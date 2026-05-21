---
title: Introduction
date: 2026-1-20
---

# Introduction

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20330479.svg)](https://doi.org/10.5281/zenodo.20330479)

Welcome to **NCAR GDEX Examples** — a collection of Jupyter notebooks that demonstrate geoscientific workflows using data from NCAR's [Geoscience Data Exchange (GDEX)](https://gdex.ucar.edu/). Each example shows how to access a specific GDEX dataset and use it for analysis or visualization, with computations performed on NCAR's HPC resources (Casper / Derecho).

:::{warning} Important Notice
This jupyter book is under active development and is intended primarily for users with access to NCAR's HPC resources (**NCAR HPC users**). All examples assume that you have access to NCAR's JupyterHub. If you are an external user trying to stream GDEX data into your own workflows, please see [osdf-examples](https://ncar.github.io/osdf-examples/) (**OSDF users**).
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

### 🌐 Multiple Access Methods

Some notebooks use intake / intake-ESM catalogs that support more than one access pattern:

- **POSIX** — direct filesystem access for NCAR HPC users
- **HTTPS** — web-based access for remote users

## Repository

Source code lives at <https://github.com/NCAR/gdex-examples>. See the [contribution guide](contribution.md) to add a new example.
