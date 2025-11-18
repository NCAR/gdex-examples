---
title: Introduction
date: 2025-11-18
---

# Introduction

Welcome to the **GDEX Examples** documentation! This repository provides example notebooks and scripts that demonstrate how to access data from NCAR's GDEX for cool geoscience applications and visualizations.

:::{warning} Important Notice
This jupyter book is under active development and is intended primarily for use by users who have access to NCAR's HPC resources. In all the examples, we assume that you have access to NCAR's jupyterhub. If you are an external user trying to stream data from NCAR's GDEX into your workflows, please see **OSDF users**: [osdf_examples](https://ncar.github.io/osdf_examples/) 
::: 

## How is the repository organized?

While intake-ESM was originally designed for Earth System Model output, we extend its capabilities to support a broader range of Earth science data including:

- **Observations** (satellite, in-situ measurements)
- **Reanalysis datasets** (ERA5, JRA-3Q, etc.)
- **Model output** (CESM, CMIP, etc.)
- **Other Earth science datasets**

## Key Features

### 🛠️ Custom Catalog Generation
Our primary tool `generator/create_catalog.py` creates intake-ESM catalogs for any dataset directory with flexible configuration options for different data formats and structures.

### 🌐 Multiple Access Methods
Generated catalogs support three access patterns :
- **POSIX**: Direct filesystem access for NCAR HPC users
- **HTTPS**: Web-based access for remote users
- **OSDF**: Distributed access through Open Science Data Federation

### 📊 Broad Dataset Support
Compatible with diverse data formats including NetCDF, Zarr, and Kerchunk reference files, following vocabulary conventions used by major data providers (DKRZ, Copernicus, NASA, NOAA).

## Quick Start

Generate a basic catalog:
```bash
python generator/create_catalog.py /path/to/data \
    --out /output/directory \
    --catalog_name my_catalog \
    --description "My dataset catalog"
```

For comprehensive usage examples:
- **NCAR HPC users**: [gdex-examples](https://ncar.github.io/gdex-examples/)
- **OSDF users**: [osdf_examples](https://ncar.github.io/osdf_examples/)

## Repository Structure

- **`generator/`** - Core catalog generation tools
- **`notebooks/`** - Example Jupyter notebooks demonstrating usage 
- **`examples/`** - Python script examples for generating dataset catalog
- **`test/`** - Test scripts and validation tools

## Content

This documentation provides:
