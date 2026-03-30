---
title: Zarr Data Format
date: 2026-3-10
---

# What is Zarr and Why Should You Care?

If you have worked with large scientific datasets — weather model output, climate simulations, radar composites — you may have run into frustrating bottlenecks: files that take forever to open, analyses that crawl because you only need a small slice of a giant file, or workflows that break when you try to run them in parallel. **Zarr** was designed to solve exactly these problems.

This page gives a beginner-friendly introduction to Zarr, what makes it different from traditional formats like NetCDF or HDF5, and when it is worth reaching for it.

---

## What is Zarr?

**Zarr** is a storage format for chunked, compressed, N-dimensional arrays. Think of it like NetCDF4 or HDF5, but built from the ground up for cloud and parallel workflows.

A Zarr *store* is not a single file. It is a **directory of small files** (or a collection of objects in cloud storage), where each small file holds one *chunk* of your data along with some lightweight metadata. This seemingly simple design decision has profound consequences for performance.

There are currently two versions of the Zarr specification in common use — **v2** and **v3** — with slightly different on-disk layouts:

| | **Zarr v2** | **Zarr v3** |
|---|---|---|
| **Group metadata** | `.zgroup` + `.zattrs` (two separate files) | `zarr.json` (single combined file) |
| **Array metadata** | `.zarray` inside each array directory | `zarr.json` inside each array directory |
| **Chunk naming** | Flat dot-separated name (e.g., `0.0.0`) | Slash-separated path under `c/` directory (e.g., `c/0/0/0`) |
| **Attributes** | Separate `.zattrs` file | Embedded in `zarr.json` |

```
# Zarr v2
my_dataset.zarr/
├── .zattrs              ← global attributes
├── .zgroup              ← marks this as a group
└── temperature/
    ├── .zarray          ← array metadata (shape, dtype, chunks, compression)
    ├── 0.0.0            ← chunk [0, 0, 0]
    ├── 0.0.1            ← chunk [0, 0, 1]
    ├── 1.0.0
    └── ...
```

```
# Zarr v3
my_dataset.zarr/
├── zarr.json            ← group metadata + attributes (replaces .zgroup + .zattrs)
└── temperature/
    ├── zarr.json        ← array metadata (replaces .zarray)
    └── c/               ← chunks directory
        ├── 0/0/0        ← chunk [0, 0, 0]
        ├── 0/0/1        ← chunk [0, 0, 1]
        ├── 1/0/0
        └── ...
```

Most datasets you will encounter on GDEX currently use **v2**. Zarr v3 is the newer standard and offers improved extensibility; both are fully supported by the Python `zarr` library.

---

## Core Concepts

### Chunks
Instead of storing data as one contiguous block, Zarr divides arrays into **chunks** — smaller rectangular sub-arrays of a chosen size. When you read a subset of the data, only the relevant chunks are loaded, not the whole dataset.

### Compression
Each chunk is independently compressed (e.g., with Blosc, Zstd, or GZip). Because compression happens per-chunk, reading one chunk never requires decompressing the rest of the dataset.

### Metadata stored as plain JSON
Array shape, data type, chunk size, and compression settings are stored in simple `.zarray` JSON files. This makes Zarr stores human-inspectable and easy to work with programmatically.

---

## Why Zarr Matters: The Key Benefits

### 1. Fast Partial Reads (Only Load What You Need)
Traditional formats like NetCDF3 store data contiguously. To read a small time slice from the middle of a large file, the library may still need to scan through a lot of data to get there. Because Zarr data is chunked and each chunk is an independent file or object, **only the chunks that overlap your requested slice are fetched**. For large datasets where you regularly work with subsets (e.g., a single variable over one region), this can be orders of magnitude faster.

### 2. Cloud-Native by Design
Zarr works naturally with object storage systems like AWS S3, Google Cloud Storage, or NCAR's own Object storage space BOREAS. Each chunk maps directly to one object/file, so cloud storage can serve many chunks in parallel with no need for special server-side range-request support. NetCDF4/HDF5 were designed for local disk and require workarounds (like kerchunk or byte-range requests) to work efficiently in the cloud.

### 3. Parallel Reads and Writes
Because each chunk is independent, **multiple processes or threads can read or write different chunks simultaneously** without locking. This makes Zarr a natural fit for Dask-based parallel workflows, which are common in Python-based geoscience computing.

### 4. Scalable to Petabyte Datasets
Zarr is used to store some of the largest publicly available Earth science datasets in existence (e.g., ERA5 on GCS, CMIP6 cloud replicas). The chunked design means the format scales without hitting the internal limits that can affect HDF5 at extreme scales.

### 5. Works Seamlessly with Xarray and Dask
Opening a Zarr store with Xarray is a single line:
```python
import xarray as xr
ds = xr.open_zarr("path/to/dataset.zarr")
```
Xarray will automatically represent the data as **lazy Dask arrays** — the data is not loaded until you actually request a computation. This lets you write analysis code against a multi-terabyte dataset on a laptop and only trigger real I/O and computation when needed.

### 6. Human-Readable Metadata
The `.zarray` and `.zattrs` files are plain JSON, so you can inspect a Zarr store's structure with nothing more than `cat` or a text editor. This is a significant debugging and discoverability advantage compared to binary formats.

---

## When Should You Use Zarr?

Zarr is not always the right choice. Here is a practical guide:

| Situation                                          | Recommendation |
|---                                                 |---|
| Data lives in cloud object storage (S3, GCS, OSDF) | **Use Zarr** — it was made for this |
| You regularly read small subsets of large arrays   | **Use Zarr** — chunk-level reads save time |
| You run parallel Dask workflows                    | **Use Zarr** — independent chunks = no write locks |
| Data is shared as a single portable file           | Consider NetCDF4 — easier to email or `scp` |
| Dataset is small (< a few GB) and read fully       | NetCDF4 or HDF5 are fine |
| Collaborators use tools that do not support Zarr   | NetCDF4 may be more compatible |

---

## A Minimal Example

```python
import numpy as np
import zarr

# Create a Zarr array on disk with chunk size (100, 100)
z = zarr.open("my_array.zarr", mode="w", shape=(1000, 1000),
              chunks=(100, 100), dtype="float32")

# Write some data
z[:] = np.random.rand(1000, 1000)

# Read a small slice — only the relevant chunks are touched
subset = z[200:250, 300:350]
print(subset.shape)  # (50, 50)
```

```python
import xarray as xr

# Open a Zarr store as an Xarray Dataset (lazy by default)
ds = xr.open_zarr("my_dataset.zarr")
print(ds)
```

---

## Further Reading

- [Zarr documentation](https://zarr.readthedocs.io/)
- [Xarray — Reading and Writing Zarr](https://docs.xarray.dev/en/stable/user-guide/io.html#zarr)
