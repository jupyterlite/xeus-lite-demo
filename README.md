# Xeus-Lite demo

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://jupyterlite.github.io/xeus-lite-demo/notebooks/?path=demo.ipynb)

This GitHub template allows you to create deployments of JupyterLite with a custom set of conda packages.

## 💡 How to make your own deployment

Creating a new deployment can be done in three easy steps:

**Step 1: Apply the GitHub template**

1. Click the **"Use this template"** button in the upper right corner of the GitHub repository.
2. Choose a name for your project and select the GitHub organization where you want to create it.
3. Then hit **"Create repository from template"** to finalize the setup.

**Step 2: Enable building the GitHub pages from GitHub actions.**

1. Once your repository is created, enable GitHub Pages by configuring GitHub Actions. This will build and deploy your site automatically.
2. Your deployment will be accessible at the following URL: https://{USERNAME}.github.io/{DEMO_REPO_NAME}.

**Step 3: Customize your conda environment**

1. Update your ``environment.yml`` file to include the required packages.
2. This ensures that your environment has all the necessary dependencies.

## 🎬 Visual Guide

For a step-by-step visual guide, check out the screencast below:

![Deploy your own](deploy.gif)

## 📦 How to install kernels and packages

You can install specific kernels and extra packages by adding them to the ``environment.yml`` file.

### Example: JupyterLite with NumPy and Matplotlib

To create a JupyterLite deployment with NumPy and Matplotlib pre-installed, edit the ``environment.yml`` file as follows:

```yml
name: xeus-kernel
channels:
  - https://repo.mamba.pm/emscripten-forge
  - conda-forge
dependencies:
  - xeus-python
  - numpy
  - matplotlib
```

### Example: JupyterLite with R and coursekata

To use the R kernel and the coursekata package, edit the environment.yml file as follows:

```yml
name: xeus-kernel
channels:
  - https://repo.mamba.pm/emscripten-forge
  - conda-forge
dependencies:
  - xeus-r
  - r-coursekata
```

### Package Compatibility

Only ``no-arch`` packages from ``conda-forge`` and packages from ``emscripten-forge`` can be installed.

- **How do I know if a package is ``no-arch`` on ``conda-forge``?** ``no-arch`` means that the package is OS-independent, usually pure-python packages are ``no-arch``. To check if your package is ``no-arch`` on ``conda-forge``, check if the "Platform" entry is "no-arch" in the https://beta.mamba.pm/channels/conda-forge?tab=packages page. If your package is not ``no-arch`` but is a pure Python package, then you should probably update the feedstock to turn your package into a ``no-arch`` one.
![](noarch.png)

- **How do I know if my package is on ``emscripten-forge``?** You can see the list of packages pubished on ``emscripten-forge`` [here](https://beta.mamba.pm/channels/emscripten-forge?tab=packages). In case your package is missing, or it's not up-to-date, feel free to open an issue or a PR on https://github.com/emscripten-forge/recipes.

