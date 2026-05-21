# gdex-examples

[![Jupyter Book](https://img.shields.io/badge/jupyter--book-live-blue?logo=jupyter)](https://ncar.github.io/gdex-examples/)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue?logo=python)](https://www.python.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20330479.svg)](https://doi.org/10.5281/zenodo.20330479)

A collection of Jupyter notebooks demonstrating geoscientific workflows that
use data from NCAR's [Geoscience Data Exchange (GDEX)](https://gdex.ucar.edu/),
with computations performed on NCAR's HPC resources (Casper / Derecho). The
site is built with [Jupyter Book 2](https://next.jupyterbook.org/) / MyST and
deployed via GitHub Pages.

**Browse the rendered book:** https://ncar.github.io/gdex-examples/

**External user, not on NCAR HPC?** This repository assumes access to NCAR's
JupyterHub on Casper / Derecho. If you want to stream GDEX data into your
own workflows from off-site, see
[osdf-examples](https://github.com/NCAR/osdf-examples).

## Quick start (NCAR HPC users)

```bash
git clone https://github.com/NCAR/gdex-examples.git
cd gdex-examples
```

Then open any notebook in `notebooks/` from NCAR JupyterHub. Each notebook
lists its required packages at the top.

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

Contributions are welcome from anyone with an NCAR HPC account or any user
of GDEX data. See the [contribution guide](docs/contribution.md) for the
full workflow.

## Support

Report bugs and request features via [GitHub Issues](https://github.com/NCAR/gdex-examples/issues).
