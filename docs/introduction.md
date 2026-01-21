---
title: Introduction
date: 2026-1-20
---

# Introduction

Welcome to the **GDEX Examples** documentation! This repository provides example notebooks and scripts that demonstrate how to access data from NCAR's GDEX for cool geoscience applications and visualizations.

:::{warning} Important Notice
This jupyter book is under active development and is intended primarily for use by users who have access to NCAR's HPC resources (**NCAR HPC users**). In all the examples, we assume that you have access to NCAR's jupyterhub. If you are an external user trying to stream data from NCAR's GDEX into your workflows, please see : [osdf_examples](https://ncar.github.io/osdf_examples/) (**OSDF users**)
::: 

## How is the repository organized?

This repository is organized by into various sections based on the type of dataset used:

- **Observations** (satellite, in-situ measurements)
- **Analysis** (NCEP GFS analyses)
- **Reanalysis** (ERA5, JRA-3Q, etc.)
- **Model output/Simulations** (CESM, CMIP, etc.)
- **Data Fusion** (Combination of two or more datasets)
- **Contribution** (A guide on contributions)

### 🌐 Multiple Access Methods
Some of these notebooks use intake/intake-ESM catalogs that support multiple access patterns :
- **POSIX**: Direct filesystem access for NCAR HPC users
- **HTTPS**: Web-based access for remote users

## Repository Structure
- **`docs/`** - Introductory markdown files for each section
- **`examples/`** - Python script examples for generating dataset catalog
