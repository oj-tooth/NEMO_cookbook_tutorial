# Resources

Below we have provided a list of useful links to documentation and data sources to support group analyses during the PROMOTE Sprint event.

---

## **Documentation**

* **OceanDataStore**

    [**https://noc-msm.github.io/OceanDataStore/**](https://noc-msm.github.io/OceanDataStore/)

* **NEMO Cookbook**

    [**https://noc-msm.github.io/nemo_cookbook/**](https://noc-msm.github.io/nemo_cookbook/)

* **xarray Tutorial**

    [**https://tutorial.xarray.dev/intro.html**](https://tutorial.xarray.dev/intro.html)

* **Flox**

    [**https://flox.readthedocs.io/en/latest/**](https://flox.readthedocs.io/en/latest/)

* **Earth & Environmental Data Science Book**

    [**https://earth-env-data-science.github.io/intro.html**](https://earth-env-data-science.github.io/intro.html)

* **Cosima Cookbook**

    [**https://cosima-recipes.readthedocs.io/en/latest/**](https://cosima-recipes.readthedocs.io/en/latest/)

---

## **Data**

### **Virtual NEMODataTrees**

A virtual NEMODataTree is a lightweight, persistent map describing how to organise our netCDF files into a `NEMODataTree` object.

For the PROMOTE Analysis Sprint, we have created virtual `NEMODataTrees` for the following simulations on JASMIN:

* **UKESM1-2-LL**: `/gws/ssde/j25b/terrafirma/otooth/repos/`

* **CANARI-LE**: `/gws/ssde/j25b/canari/shared/large-ensemble/ocean/repos/`

To access virtual `NEMODataTrees`, we can use the `.from_icechunk()` constructor:

```python
# Step 1. Authorise Icechunk to fetch virtual chunks from the original netCDF files on JASMIN terrafirma group workspace:
store_fpath = "/gws/ssde/j25b/terrafirma"
credentials = icechunk.credentials.containers_credentials({f"file://{store_fpath}/": icechunk.credentials.LocalFileSystemAccess})

# Step 2. Open Icechunk repository stored on JASMIN terrafirma group workspace:
repo_fpath = f"/gws/ssde/j25b/terrafirma/otooth/repos/UKESM1-2-LL_{experiment}_{member}"
repo = icechunk.Repository.open(storage=icechunk.local_filesystem_storage(repo_fpath),
                                authorize_virtual_chunk_access=credentials
                                )

# Step 3. Create virtual NEMODataTree from Icechunk repository:
nemo = NEMODataTree.from_icechunk(repo=repo,
                                    branch="main",
                                    iperio=True,
                                    nftype="F",
                                    name=f"UKESM1-2-LL_{experiment}_{member}",
                                    open_kwargs={"decode_times": CFDatetimeCoder(time_unit="s"),
                                                 "chunks": {},
                                                 }
                                    )
```

### **Ocean Observations**

The observational datasets below are publicly accessible via the **OceanDataStore**.

After activating one of the shared `env_nemo` virtual environments, we can create a new instance of the **OceanDataCatalog** to access available ocean observations as follows:

```python
from OceanDataStore import OceanDataCatalog

catalog = OceanDataCatalog(catalog_name="noc-stac")
```

where `noc-stac` is the default National Oceanography Centre ocean model Spatio-Temporal Access Catalog.

---

**NSIDC Observations**
    
For further details, see NSIDC [**here**](https://nsidc.org/data/g02135/versions/4).

**Access** 

- Antarctic Monthly Sea Ice Timeseries:
```python
catalog.open_dataset(id="nsidc/nsidc_sea_ice_index_v4_antarctic_monthly")
```

- Arctic Monthly Sea Ice Timeseries:
```python
catalog.open_dataset(id="nsidc/nsidc_sea_ice_index_v4_arctic_monthly")
```

---

**HadISST Observations**
    
For further details, see HadISST [**here**](https://www.metoffice.gov.uk/hadobs/hadisst/).

**Access** 

- HADISST v1.1 Monthly Sea Surface Temperature & Sea Ice Timeseries:
```python
catalog.open_dataset(id="hadisst/hadisst_v1.1_monthly")
```

---

**OISSTv2 Observations**
    
For further details, see OISSTv2 [**here**](https://psl.noaa.gov/data/gridded/data.noaa.oisst.v2.highres.html).

**Access** 

- OISST v2.1 Monthly Sea Surface Temperature & Sea Ice Timeseries:
```python
catalog.open_dataset(id="oisst/oisst_v2.1_monthly")
```

---

**EN4.2.2 Analysis**
    
For further details, see EN4.2.2 [**here**](https://www.metoffice.gov.uk/hadobs/en4/download-en4-2-2.html).

**Access** 

- EN4.2.2 Monthly Timeseries:
```python
catalog.open_dataset(id="en4.2.2/en4.2.2_analysis_g10_monthly")
```

- EN4.2.2 Monthly Climatologies:
```python
catalog.open_dataset(id="en4.2.2/en4.2.2_analysis_g10_1971_2000_monthly_climatology")

catalog.open_dataset(id="en4.2.2/en4.2.2_analysis_g10_1981_2010_monthly_climatology")

catalog.open_dataset(id="en4.2.2/en4.2.2_analysis_g10_1991_2020_monthly_climatology")
```

---

**ARMOR-3D Analysis**
    
For further details, see ARMOR-3D [**here**](https://data.marine.copernicus.eu/product/MULTIOBS_GLO_PHY_TSUV_3D_MYNRT_015_012/description).

**Access** 

- ARMOR-3D Monthly Timeseries:
```python
catalog.open_dataset(id="armor3d/armor3d_global_my_monthly")
```

- ARMOR-3D Monthly Climatologies:
```python
catalog.open_dataset(id="armor3d/armor3d_global_my_1971_2000_monthly_climatology")

catalog.open_dataset(id="armor3d/armor3d_global_my_1981_2010_monthly_climatology")

catalog.open_dataset(id="armor3d/armor3d_global_my_1991_2020_monthly_climatology")
```

---

**RAPID Observations**
    
For further details, see RAPID Data [**here**](https://rapid.ac.uk/data).

**Access** 

```python
xr.open_zarr("https://noc-msm-o.s3-ext.jc.rl.ac.uk/ocean-obs/RAPID/{dataset}", zarr_format=3)
```

**Available Datasets:**

* 2d_gridded_v2024.1/
* fc_transport_adj_v3/
* meridional_transports_v2024.1/
* moc_transports_v2024.1/
* moc_vertical_v2024.1/
* mocha_mht_data_ERA5_v2020/
* ts_gridded_v2024.1/

---

**OSNAP Observations**
    
For further details, see OSNAP Data [**here**](https://www.o-snap.org/data-access/).

**Access** 

```python
xr.open_zarr("https://noc-msm-o.s3-ext.jc.rl.ac.uk/ocean-obs/OSNAP/{dataset}", zarr_format=3)
```

**Available Datasets:**

* OSNAP_Gridded_TSV_201408_202207_2025/
* OSNAP_MOC_MHT_MFT_TimeSeries_201408_202207_2025/
* OSNAP_Streamfunction_201408_202207_2025/

---

**World Ocean Atlas 2023 Analysis**

For further details, see World Ocean Atlas [**here**](https://www.ncei.noaa.gov/access/world-ocean-atlas-2023/).

**Access** 

- World Ocean Atlas 2023 Monthly Climatologies:
```python
catalog.open_dataset(id="woa23/woa23_1971_2000_monthly_climatology")

catalog.open_dataset(id="woa23/woa23_1981_2010_monthly_climatology")

catalog.open_dataset(id="woa23/woa23_1991_2020_monthly_climatology")
```
