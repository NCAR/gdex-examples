---
title: Reanalysis
date: 2025-12-05
author: Chia-Wei Hsu
---


## Overview

Reanalysis products are comprehensive datasets that combine historical observations with models simulation to create a consistent, spatially and temporally complete representation of the Earth's past climate and weather. They are one of the most valuable resources in Earth system science for understanding climate variability, trends, and dynamics.

## Reanalysis vs. Analysis vs. Simulations vs. Observations

Understanding the differences between these fundamental data types is crucial for Earth system science research.

:::{important} Reanalysis vs. Analysis 👈
:class: dropdown
**Analysis** refers to the real-time, operational data assimilation product produced by weather forecasting centers:
- Uses the **current** version of the forecast model and assimilation system
- The model and assimilation methods **change over time** as improvements are made
- Optimized for short-term weather forecasting
- Creates discontinuities when the system is upgraded

**Reanalysis** retrospectively processes historical observations:
- Uses a **fixed** model and assimilation system for the entire time period
- Ensures temporal **consistency** and homogeneity
- Not updated in real-time; produced in multi-year projects
- Better suited for climate studies and long-term trend analysis
- More computationally expensive due to reprocessing decades of data

**Key Distinction**: Analysis prioritizes current forecast skill; reanalysis prioritizes long-term consistency.
:::

:::{important} Reanalysis vs. Model Simulations 👈
:class: dropdown
**Model Simulations** (also called free-running simulations or climate projections):
- Run forward in time without observational constraints
- Initial conditions may come from observations, but the model evolves freely
- Used for future climate projections and sensitivity experiments
- Can drift from observed climate due to model biases
- Examples: CMIP6 models, CESM simulations

**Reanalysis**:
- **Continuously constrained** by observations through data assimilation
- Cannot drift far from observed atmospheric state
- Represents the "best estimate" of what actually happened
- Limited to historical periods where observations exist
- Blends model physics with observational evidence

**Key Distinction**: Simulations show what the model thinks should happen; reanalysis shows what actually happened (constrained by observations).
:::


:::{important} Reanalysis vs. Observations 👈
:class: dropdown
**Direct Observations** (in-situ and remote sensing):
- Actual measurements from instruments
- **Highest accuracy** at measurement location and time
- Spatially and temporally **incomplete** (gaps between stations, satellite swaths)
- Different instruments have different biases and uncertainties
- No information about unobserved variables or locations
- Examples: Weather station data, satellite retrievals, radiosonde profiles

**Reanalysis**:
- **Gridded, gap-filled** product combining observations with model physics
- Provides estimates even where/when no observations exist
- Spatially and temporally **complete**
- Includes hundreds of variables, many not directly observed
- **Less accurate** than direct observations at observed locations
- Smooths out small-scale features
- Subject to both observational and model uncertainties

**Key Distinction**: Observations provide ground truth but are incomplete; reanalysis provides complete coverage but is less accurate than direct observations.
:::



## How Reanalysis Works

### Data Assimilation Process

Reanalysis uses a process called **data assimilation** to blend:

1. **Observational Data**: Including satellite measurements, weather stations, radiosondes (weather balloons), ship and buoy observations, and aircraft reports
2. **Numerical Models**: Physics-based models that simulate atmospheric, oceanic, and land surface processes

The data assimilation system statistically combines these elements, weighing observations and model predictions based on their respective uncertainties to produce the "best estimate" of the atmospheric state at any given time.

### Key Characteristics

- **Temporal Consistency**: Uses a fixed, modern assimilation system and model throughout the entire reanalysis period.
- **Spatial Completeness**: Fills gaps where observations are sparse or unavailable using model physics
- **Regular Grid**: Produces data on uniform spatial and temporal grids, making it easier to analyze
- **Multiple Variables**: Provides hundreds of atmospheric, oceanic, and land variables that are physically consistent with each other

## Types of Reanalysis

### Atmospheric Reanalysis
- **ERA5** (ECMWF): Currently the most widely used, covering 1940-present
- **JRA-3Q** (JMA): Japanese reanalysis with high-quality precipitation estimates

### Ocean Reanalysis
- **ORAS5**: Ocean reanalysis system

### Coupled Reanalysis
- **CERA-20C**: 20th century coupled reanalysis

## Applications in Earth System Science

Reanalysis products are used for:

1. **Climate Monitoring**: Tracking long-term temperature, precipitation, and circulation patterns
2. **Extreme Event Analysis**: Studying hurricanes, droughts, heat waves, and other extreme weather
3. **Model Validation**: Evaluating climate and weather models against a consistent reference
4. **Forcing Data**: Driving regional models, hydrological models, and impact assessments
5. **Process Studies**: Understanding physical mechanisms and teleconnections
6. **Trend Analysis**: Identifying climate change signals and natural variability
7. **Deep Learning/Machine Learning**: Training and validating AI-based weather and climate models


## Limitations and Considerations

### Observational Network Changes
- Early periods (pre-satellite era) have fewer observations and higher uncertainty
- Introduction of new satellite systems can create discontinuities

### Model Biases
- The underlying numerical model has systematic biases that affect the reanalysis
- Variables directly constrained by observations (temperature, wind) are more reliable than derived quantities (precipitation, evaporation)

### Spurious Trends
- Some trends may be artifacts of changing observational systems rather than real climate signals
- Multiple reanalysis products should be compared for robust conclusions

### Resolution Limitations
- Even high-resolution reanalysis cannot resolve all small-scale features
- Convective processes and orographic effects may be inadequately represented

## Best Practices

When using reanalysis data:

1. **Choose the Right Product**: Consider temporal coverage, spatial resolution, and which variables are best represented
2. **Validate Carefully**: Compare with independent observations when possible
3. **Use Multiple Products**: Cross-validate findings across different reanalysis systems
4. **Understand Uncertainty**: Be aware of which variables are observation-constrained vs. model-derived
5. **Check Documentation**: Review known issues and dataset updates from producing centers

## Resources

Major reanalysis centers provide extensive documentation:
- [ECMWF ERA5 Documentation](https://confluence.ecmwf.int/display/CKB/ERA5)
- [JMA JRA-3Q Documentation](https://jra.kishou.go.jp/)

