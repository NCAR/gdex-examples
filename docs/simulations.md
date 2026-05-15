---
title: Simulations
date: 2026-1-20
---

# Simulations

## Overview

**Model simulations** (also called free-running simulations) are outputs from physics-based Earth system models that integrate forward in time without continuous observational constraint. They are the principal tool for studying climate variability, climate sensitivity, and future projections — and they make up a large fraction of the data hosted on NCAR's GDEX.

This section demonstrates how to access simulation output and use it for scientific analysis.

## Characteristics

- **Forward integration** — once initialized, the model evolves under its own physics
- **No observational constraint during runtime** — the model can drift from observed climate because of physics biases
- **Large ensembles** — many simulations are run as ensembles (different initial conditions or parameter perturbations) to characterize internal variability and uncertainty
- **Multiple scenarios** — projections often span several forcing pathways (e.g., SSP1-2.6, SSP5-8.5)
- **Physically consistent** — variables are coupled through the model equations, so derived quantities (energy and water budgets) close

## Datasets in this section

- **CESM2 Large Ensemble (LENS)** — 100-member ensemble of the Community Earth System Model; used here for GMST anomaly, ocean heat content, and GeoCAT-based visualization examples.
- **NA-CORDEX** — North American CORDEX downscaled regional climate simulations.

## Where to start

If you are new to CESM or large-ensemble analysis, start with the [CESM GMST notebook](../notebooks/cesm_gmst_ncar.ipynb), which walks through computing the ensemble-mean global-mean surface-temperature anomaly from LENS.

## Related sections

- See [Reanalysis](reanalysis.md) for the observationally constrained counterpart to free-running simulations.
- See [Data Fusion](data_fusion.md) for examples that combine simulation output with observations.
