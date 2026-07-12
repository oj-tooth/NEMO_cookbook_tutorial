# Getting Started

To participate in the hands-on tutorials and get started exploring the outputs of the NOC Near-Present Day simulations, we strongly recommend that participants use the one of the pre-prepared Python virtual environments which contain all of the required Python packages already.

### Downloading Tutorials

Let's start by making a local copy of the `NEMO_Cookbook_tutorial` GitHub repository containing the Jupyter Notebooks used in the tutorial. 

```bash
# Navigate to your chosen working directory, and then clone the GitHub repo:
git clone https://github.com/promote-project/NEMO_cookbook_tutorial.git
```

Once the download is complete, you will see that a new `NEMO_cookbook_tutorial` directory has been added to your working directory.

Inside `NEMO_cookbook_tutorial`, you will find:

* `/docs` - Documentation source files for this [**NEMO Cookbook Tutorial website**](https://promote-project.github.io/nemo_cookbook_tutorial/)

* `/tutorials` - Jupyter Notebooks for NEMO Cookbook Tutorials

!!! note

    Editing any of the tutorial or example notebooks / creating new notebooks in your cloned `NEMO_cookbook_tutorial` will not impact the original GitHub repository.

### Configuring Jupyter Kernel

To get started running the tutorial notebooks, you need to set-up a Jupyter Kernel - the computational engine for your Python code.

We have already installed all of the necessary packages for the tutorial notebooks in two shared Conda environment accessible by everyone with `terrafirma` or `canari` group workspace access on **JASMIN**.

??? info "What is Conda?"

    Conda is a package manager which allows users to install software packages into dedicated virtual environments. This enables us to create different virtual environments, including different versions of the same software, for separate projects. 

    Virtual environments can also be shared between users by exporting them to a `.yml` file, which can be used to re-create the environment on another computer.

    Conda is especially suited to scientific software applications since it can handle complex dependencies and pre-compiled binaries (e.g., netCDF4 to read netCDF files)

    There are many different types of Conda package manager available:

    * **Anaconda** - Includes lots of common software, requires paid license.
    * **Miniconda** - Minimal version of Anaconda.
    * **Miniforge** - Minimal Conda package manager using only conda-forge (community) channel, exempt from licensing above.

To install a Jupyter kernel for the `env_nemo` shared Conda environment, run one of the following commands in your terminal:

```bash
# CANARI GWS:
/gws/ssde/j25b/canari/public/env_nemo/bin/python -m ipykernel install --user --name env_nemo --display-name "PROMOTE Sprint (env_nemo)"
```

```bash
# TERRAFIRM GWS:
/gws/ssde/j25b/terrafirma/otooth/env_nemo/bin/python -m ipykernel install --user --name env_nemo --display-name "PROMOTE Sprint (env_nemo)"
```

This will add a new Jupyter kernel called `env_nemo` to your kernelspec.

Now, when we open a Jupyter Notebook (e.g., `tutorials/tutorial_0_getting_started_with_nemo_cookbook.ipynb`), we will see a **Select Kernel** drop-down menu and included in the list is `PROMOTE Sprint (env_nemo)` kernel.
