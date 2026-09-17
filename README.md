# gdex-examples

[![Jupyter Book](https://img.shields.io/badge/jupyter--book-live-blue?logo=jupyter)](https://ncar.github.io/gdex-examples/)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue?logo=python)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20330479.svg)](https://doi.org/10.5281/zenodo.20330479)
[![Binder](https://binder.k8s.ucar.edu/badge_logo.svg)](https://binder.k8s.ucar.edu/v2/gh/NCAR/gdex-examples/main)

A collection of Jupyter notebooks demonstrating geoscientific workflows that
use data from NCAR's [Geoscience Data Exchange (GDEX)](https://gdex.ucar.edu/).
Each notebook auto-detects its environment and runs on NCAR HPC (Casper /
Derecho), on CIRRUS BinderHub, or on your own laptop — reading data over the
fast POSIX mount where `/gdex/data` is available and otherwise streaming it
over OSDF. The site is built with
[Jupyter Book 2](https://next.jupyterbook.org/) / MyST and deployed via
GitHub Pages.

**Browse the rendered book:** https://ncar.github.io/gdex-examples/

**Not on NCAR HPC?** Many notebooks run anywhere: click the **Binder** badge
above to launch the repository on CIRRUS BinderHub, or run them locally —
off-cluster they stream GDEX data over OSDF, so no filesystem mount is needed.

## Quick start

```bash
git clone https://github.com/NCAR/gdex-examples.git
cd gdex-examples
```

Then open any notebook in `notebooks/` — on NCAR JupyterHub, on
[CIRRUS BinderHub](https://binder.k8s.ucar.edu/v2/gh/NCAR/gdex-examples/main),
or locally in a `conda`/`mamba` environment built from `environment.yml`. Each
notebook auto-detects where it is running, so no edits are needed. Each notebook
also lists its required packages at the top.

## What's inside

Examples are organized by data type:

- **Observations** — direct measurements (HadISST, EOL radar, ...)
- **Analysis** — operational data-assimilation products (NCEP GFS)
- **Reanalysis** — retrospectively assimilated records (ERA5, JRA-3Q, DART/CAM6)
- **Simulations** — model output (CESM2 LENS, NA-CORDEX, ...)
- **Data Fusion** — workflows combining two or more datasets
- **Background & Concepts** — supporting material (e.g. the Zarr format)

See the [Introduction](docs/introduction.md) for a fuller tour.

## Repository structure

```
docs/         Section overviews and the contribution guide
notebooks/    All example workflow notebooks
myst.yml      Jupyter Book 2 configuration / table of contents
```

## How to contribute

Contributions are welcome from anyone who uses GDEX data. See the
[contribution guide](docs/contribution.md) for the full workflow.

## Support

Report bugs and request features via [GitHub Issues](https://github.com/NCAR/gdex-examples/issues).
