# Tutorials

During the PROMOTE Analysis Sprint, we will be running hands-on tutorials to demonstrate how to use NEMO Cookbook to analyse NEMO ocean model outputs from UKESM1-2-LL and the CANARI Large-Ensemble.

For those with limited Python experience, we would recommend working through **Tutorial 0. Getting Started with xarray** prior to the hackathon to better understand the key data structures and operations used throughout the hackathon.

---

### **Pre-Hackathon**

* **0. Getting Started with xarray**

    Ocean models produce large, multi-dimensional fields (e.g. temperature, salinity, velocity) that vary in time and space and are described by physical coordinates (e.g., depth). [**xarray**](https://docs.xarray.dev/en/stable/) provides data structures that explicitly represent these dimensions and coordinates, rather than treating model outputs as anonymous multi-dimensional arrays.

    This Jupyter Notebook provides an introduction to xarray for ocean model analysis and is intended as a quick reference that you can return to during the hackathon and beyond.

---

### **NEMO Cookbook Tutorials**

* **1. Getting Started with NEMO Cookbook.**

    In this Jupyter Notebook, we will demonstrate how to use the `NEMODataTree` object to analyse outputs of NEMO global ocean sea-ice simulations.

    We will cover:

    * Creating `NEMODataTree` objects directly from netCDF files and `xarray.Datasets`.

    * Opening virtual `NEMODataTrees` from Icechunk repositories.

    * Exploring NEMO model output variables stored in a `NEMODataTree`.

    * Geographical plotting of NEMO output variables.

    * Perform grid-aware operations using `NEMODataArrays`.

* **2. Analysing UKESM1-2-LL with NEMO Cookbook.**

    In this Jupyter Notebook, we will demonstrate how to use the `NEMODataTree` object to analyse outputs of the TERRAFIRMA UKESM1-2-LL idealised emission scenario simulations on JASMIN.

    We will cover:

    * Opening virtual `NEMODataTree` objects directly from Icechunk repositories using the `from_icechunk()` constructor.

    * Exploring NEMO ocean & sea-ice variables stored in a `NEMODataTree`.

    * Calculating March mixed layer volume for the subpolar North Atlantic using `NEMODataArray.integral()`.

* **3. Analysing CANARI Large-Ensemble with NEMO Cookbook.**

    In this Jupyter Notebook, we will demonstrate how to use the `NEMODataTree` object to analyse outputs of the CANARI Large-Ensemble simulations on JASMIN.

    We will cover:

    * Opening virtual `NEMODataTree` objects directly from Icechunk repositories using the `from_icechunk()` constructor.

    * Exploring NEMO ocean & sea-ice variables stored in a `NEMODataTree`.

    * Extracting the North Atlantic Changes (NOAC) 47°N array using `NEMODataTree.extract_zonal_section()`.
