# Contributing to NCAR GDEX Examples

We welcome contributions from anyone who has an NCAR HPC account (Casper/Derecho access) or simply uses GDEX data! This guide will walk you through the process of contributing your geoscientific workflow examples to the repository.

## Contribution Workflow

### Step 1: Fork the Repository

1. Navigate to the [NCAR gdex-examples repository](https://github.com/NCAR/gdex-examples)
2. Click the **Fork** button in the upper right corner
3. This creates a copy of the repository under your GitHub account

### Step 2: Clone Your Fork Locally

```bash
# Clone your forked repository to your local machine
git clone https://github.com/YOUR-USERNAME/gdex-examples.git
cd gdex-examples

# Add the upstream repository as a remote
git remote add upstream https://github.com/NCAR/gdex-examples.git
```

### Step 3: Create a Feature Branch

Always create a new branch for your contributions:

```bash
# Create and switch to a new branch
git checkout -b example/my-dataset-example
```

Use a descriptive branch name that reflects your contribution (e.g., `example/cesm-analysis`, `example/era5-comparison`).

### Step 4: Make Your Changes

#### Adding a New Example Notebook

1. **Use the Template**: Start with the [template notebook](../notebooks/template.ipynb) as your foundation
2. **Place Your Notebook**: Add your Jupyter notebook to the `notebooks/` directory
3. **Follow Naming Conventions**: Use descriptive, lowercase names with underscores (e.g., `my_dataset_analysis.ipynb`)
4. **Include Images**: If your notebook uses images, place them in `docs/images/` with descriptive filenames

#### Notebook Requirements

Your notebook should include:

- **Author and Date**: Fill in the YAML header with your name and date
- **Dataset Information**: Clear identification of the GDEX dataset being used
- **Required Packages**: List all necessary packages for reproducibility
- **Data Access Method**: Specify the Data URL and/or GDEX POSIX path
- **Clear Research Question**: Define what your example demonstrates
- **Step-by-Step Workflow**: Include clear sections with explanations
- **Visualizations**: Add meaningful plots or outputs that demonstrate the workflow

### Step 5: Test Your Notebook

Before submitting, ensure your notebook:

- Runs completely from top to bottom without errors
- Uses data accessible through GDEX
- Can be executed on NCAR's Casper HPC resource if applicable 
- Follows the structure and style of existing examples

### Step 6: Commit Your Changes

```bash
# Stage your changes
git add notebooks/my_dataset_analysis.ipynb
git add docs/images/my_figure.png  # if applicable

# Commit with a descriptive message
git commit -m "Add example workflow for [Dataset Name] analysis"
```

### Step 7: Push to Your Fork

```bash
# Push your branch to your forked repository
git push origin example/my-dataset-example
```

### Step 8: Submit a Pull Request

1. Go to your forked repository on GitHub
2. Click the **Compare & pull request** button
3. Provide a clear title and description:
   - What dataset does your example use?
   - What scientific question or workflow does it demonstrate?
   - Any special requirements or dependencies?
4. Submit the pull request to merge into the upstream NCAR gdex-examples repository

### Step 9: Address Review Feedback

- Repository maintainers may request changes or improvements
- Make additional commits to your branch to address feedback
- Push the updates, and they will automatically appear in your PR

## Best Practices

### Code Quality

- **Clean Code**: Remove debugging code and unnecessary outputs
- **Comments**: Add clear comments explaining complex operations
- **Reproducibility**: Ensure paths and data references work on NCAR systems

### Documentation

- **Descriptive Text**: Use markdown cells to explain each step
- **Citations**: Reference relevant papers or datasets
- **Links**: Provide links to GDEX dataset pages

### Performance

- **Efficient Code**: Optimize for performance on Casper
- **Data Subset**: Use reasonable data subsets for examples (avoid processing entire datasets unnecessarily)
- **Memory Management**: Be mindful of memory usage

## Getting Help

- **Bugs**: Report bugs via GitHub Issues with detailed reproduction steps
- **Discussions**: Use GitHub Discussions for broader topics

## Template Reference

For a complete guide on structuring your notebook, see the [example template](../notebooks/template.ipynb) in the next section. This template provides:

- Section structure for workflow documentation
- Examples of including images and figures
- Data access code patterns
- Standard admonitions and callouts

## Code of Conduct

Please be respectful and constructive in all interactions. We aim to foster an inclusive and collaborative community.

## License

By contributing to this repository, you agree that your contributions will be licensed under the same license as the project.

---

Thank you for contributing to the NCAR GDEX Examples! Your workflows help the broader geoscience community leverage GDEX data effectively.
