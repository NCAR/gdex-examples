# gdex-examples

## About
Geoscientific workflow examples that ingest data from NCAR's Geoscience Data Exchange (GDEX) and use NCAR's HPC resource Casper for computation. This repo is under active development and a future stable version will use Jupyter Book 2 infrasturcture to publish these example notebooks as a cookbook.

## Example Workflows
1) Access CESM2 LENS data from GDEX [compute](notebooks/cesm_gmst_ncar.ipynb) GMST anomaly and plot.
2) Access NA-CORDEX data from NCAR's GDEX and make some diagnostic [plots](notebooks/na_cordex.ipynb)
3) Use DART reanalysis data to make [diagnostic plots](notebooks/dart-cam6.ipynb)
4) Read EOL profiler data from GDEX and [compare](notebooks/eol_test.ipynb) with ERA5 reanalysis

## How to contribute 
We welcome contributions from anyone who has an NCAR HPC account (Casper/Derecho access) and uses GDEX data! Please follow these steps:
1. Fork the repository
2. Create a feature branch (git checkout -b example/my-amazing-example)
3. Add your notebook/ workflow
4. Submit a pull request with a brief explanation of the changes

## Support
Issues: Please report bugs and feature requests via GitHub Issues
Contact: @hrhampapura 
