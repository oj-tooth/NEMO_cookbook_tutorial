<p align="left">
    <img src="./docs/docs/assets/icons/promote_logo.png" alt="Logo" width="100" height="100">
</p>

## **NEMO Cookbook Tutorial** - PROMOTE Analysis Sprint

**Last Updated: 13/07/2026**

### **PROMOTE Analysis Sprint**

The PROMOTE project (Progressing Earth System Modelling for Tipping Point Early Warning Systems) is funded under ARIA’s 'Forecasting Tipping Points' programme.

One goal of PROMOTE is to assess the plausibility of tipping processes and physical/biogeochemical impacts of tipping as represented in UK Earth System Model (UKESM) and its component models.

The **PROMOTE Analysis Sprint** is a week of focussed model evaluation by the PROMOTE team to advance these assessments.

### **NEMO Cookbook Tutorial**

> **10:40-11:40 - Monday 13th July 2026**

As part of the [PROMOTE Analysis Sprint](https://promote-project.github.io/promote_analysis_sprint_2026/) 13th-17th July 2026, we'll be delivering a hands-on tutorial to introduce participants to the NEMO Cookbook open-source Python library for reproducible analysis and validation of NEMO ocean model outputs.

:book: [**Tutorial Documentation**](https://oj-tooth.github.io/NEMO_cookbook_tutorial/)

#### **What is NEMO Cookbook?**

NEMO Cookbook extends the familiar xarray data model with grid-aware data structures designed for performing reproducible analyses of the Nucleus for European Modelling of the Ocean (NEMO) ocean general circulation model outputs.

Our aim is to provide a collection of recipes implementing the post-processing & analysis functions available in CDFTOOLS alongside new diagnostics (e.g., surface-forced water mass transformation), which are compatible with generalised vertical coordinate systems (e.g., MES).

Each recipe uses the `NEMODataTree` and `NEMODataArray` structures to leverage xarray, flox & dask libraries (think of these are your cooking utensils) to calculate a diagnostic with NEMO ocean model outputs (i.e., the raw ingredients - that's where you come in!).

### **Contributors**

- **Ollie Tooth** (oliver.tooth@noc.ac.uk)
- **Adam Blaker** (atb299@noc.ac.uk)
- **Andrew Coward** (acc@noc.ac.uk)

### **Funding**

The ongoing development of NEMO Cookbook is funded by the following projects: 

- **AtlantiS**: [Atlantic Climate and Environment Strategic Science](https://atlantis.ac.uk)
- **ARIA - PROMOTE**: [Progressing earth system Modelling for Tipping Point Early warning systems](https://aria.org.uk/opportunity-spaces/scoping-our-planet/forecasting-tipping-points/)
- **EPOC**: [Explaining & Predicting the Ocean Conveyor](https://epoc-eu.org)
