---

# Introduction

Welcome to the **GDEX Examples** documentation! This repository provides example notebooks and scripts that demonstrate how to access data from NCAR's GDEX for cool geoscience applications and visualizations.

:::{warning} Important Notice
This jupyter book is under active development and is intended primarily for use by users who have access to NCAR's HPC resources. In all the examples, we assume that you have access to NCAR's jupyterhub. If you are an external user trying to stream data from NCAR's GDEX into your workflows, please see **OSDF users**: [osdf_examples](https://ncar.github.io/osdf_examples/) 
::: 

## How is the repository organized?

This repository is organized by into various :

- **Observations** (satellite, in-situ measurements)
- **Reanalysis datasets** (ERA5, JRA-3Q, etc.)
- **Model output** (CESM, CMIP, etc.)
- **Other Earth science datasets**

### 🌐 Multiple Access Methods
Generated catalogs support three access patterns :
- **POSIX**: Direct filesystem access for NCAR HPC users
- **HTTPS**: Web-based access for remote users
- **OSDF**: Distributed access through Open Science Data Federation

## Quick Start
For comprehensive usage examples:
- **NCAR HPC users**: [gdex-examples](https://ncar.github.io/gdex-examples/)
- **OSDF users**: [osdf_examples](https://ncar.github.io/osdf_examples/)

## Repository Structure
- **`docs/`** - Introductory markdown files for each section
- **`examples/`** - Python script examples for generating dataset catalog

## Content

This documentation provides:
