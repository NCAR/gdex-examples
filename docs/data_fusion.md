---
title: Data Fusion
date: 2025-11-18
---

# Data Fusion

## Overview

**Data fusion** workflows combine two or more datasets — often of different types (e.g., observations + reanalysis, or simulation output + observed indices) — to answer questions that no single dataset can answer alone. Fusion is where most applied geoscience lives: validating a model against observations, deriving a downstream metric that depends on several variables, or constructing a long record from a patchwork of sources.

This section demonstrates fusion workflows using data from NCAR's GDEX and, where relevant, external repositories.

## Common reasons to fuse data

- **Validation** — compare a model or reanalysis variable against direct observations
- **Bias correction** — adjust simulation output toward an observational reference distribution
- **Derived quantities** — compute indices (e.g., heat index, drought index) that combine multiple variables from different sources
- **Gap-filling** — patch missing observations with model fields

## Things to watch out for

- **Grid mismatch** — different datasets sit on different spatial and temporal grids; regridding choices can drive results
- **Time alignment** — instantaneous vs. averaged vs. accumulated fields can carry different timestamps for the same nominal time
- **Unit and convention differences** — Kelvin vs. Celsius, accumulated vs. rate-based precipitation, pressure-level vs. model-level
- **Independence** — reanalysis already ingests many observations, so it is not strictly independent from observational records you might use to validate it

## Datasets in this section

- **EOL profiler + ERA5** — comparing in-situ profiler observations against ERA5 reanalysis
- **JJA Heat Index** — combining temperature and humidity fields to compute a derived heat-stress index

## Where to start

The [EOL profiler vs. ERA5 notebook](../notebooks/eol_era5.ipynb) is a clean example of the observation-vs-reanalysis comparison pattern.

## Related sections

- See [Observations](observations.md) and [Reanalysis](reanalysis.md) for background on the source data types most commonly fused.
