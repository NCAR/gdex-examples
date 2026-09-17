---
title: Introduction
date: 2026-1-20
---

# Introduction

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20330479.svg)](https://doi.org/10.5281/zenodo.20330479)

Welcome to **NCAR GDEX Examples** — a collection of Jupyter notebooks that demonstrate geoscientific workflows using data from NCAR's [Geoscience Data Exchange (GDEX)](https://gdex.ucar.edu/). Each example shows how to access a specific GDEX dataset and use it for analysis or visualization.

:::{note} Run these anywhere
Each notebook **auto-detects its environment**: it reads data over the fast POSIX mount where `/gdex/data` is available (NCAR HPC, CIRRUS BinderHub) and otherwise streams it over the [Open Science Data Federation (OSDF)](https://osg-htc.org/services/osdf.html). The examples run on NCAR JupyterHub, on CIRRUS BinderHub, or on your own laptop with no code changes.
:::

## How is the site organized?

Examples are grouped into sections by data type:

- **Observations** — satellite, in-situ measurements
- **Analysis** — NCEP GFS analyses
- **Reanalysis** — ERA5, JRA-3Q, etc.
- **Simulations** — model output (CESM, CMIP, etc.)
- **Data Fusion** — combinations of two or more datasets
- **Background & Concepts** — supporting material (e.g., the Zarr format)
- **Contribution** — guide for adding new examples

### 🌐 Runs on HPC, Binder, or your laptop

Every notebook auto-detects where it is running and picks the data path for you:

- **POSIX** — direct filesystem access where `/gdex/data` is mounted (NCAR HPC, CIRRUS BinderHub)
- **OSDF** — streamed over the Open Science Data Federation when off-cluster (laptops, other hubs)

No edits are needed to move between them.

## Repository

Source code lives at <https://github.com/NCAR/gdex-examples>. See the [contribution guide](contribution.md) to add a new example.
