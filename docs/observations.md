---
title: Observations
date: 2026-1-20
---

# Observations

## Overview

Observational datasets are **direct measurements** of the Earth system from instruments such as weather stations, radiosondes, buoys, radars, and satellites. They provide the closest representation of the actual atmospheric, oceanic, or land state available — but only at the locations and times the instruments operate.

This section demonstrates how to access observational datasets hosted on NCAR's GDEX and use them in geoscientific workflows.

## Characteristics of observational data

- **Highest accuracy at the point of measurement** — within instrument error bars
- **Spatially and temporally incomplete** — gaps between stations, satellite swath limits, missing data during instrument outages
- **Heterogeneous** — different instruments have different biases, units, sampling cadence, and quality flags
- **Limited to what is observed** — derived variables (e.g., latent heat flux) are usually unavailable and must come from a model

## Datasets in this section

- **HadISST** — Hadley Centre Sea Ice and Sea Surface Temperature dataset; monthly 1°×1° SST and sea ice, 1870–present. Used here for El Niño / ENSO analysis.
- **EOL Radar Precipitation** — NCAR Earth Observing Laboratory precipitation radar observations.
- **RAF flight track** — NCAR Research Aviation Facility flight observation for Southern Ocean Clouds Radiation Aerosol Transport Experimental Study (SOCRATES).

## Where to start

If you are new to working with GDEX observational data, start with the [HadISST El Niño notebook](../notebooks/hadisst_elnino.ipynb), which shows how to load gridded SST observations, define an ENSO index, and visualize ENSO phases.

## Related sections

- See [Reanalysis](reanalysis.md) for gridded, gap-filled products that combine observations with model physics.
- See [Data Fusion](data_fusion.md) for examples that combine observations with reanalysis or simulation output.
