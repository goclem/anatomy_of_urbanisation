# Data package

**Paper**: [An Anatomy of Urbanization in Sub-Saharan Africa](https://documents1.worldbank.org/curated/en/099415311272320571/pdf/IDU0faef6c000aaba0485209f0e08928760d9a57.pdf)

**Authors:**

- [Pierre-Philippe Combes](mailto:pierrephilippe.combes@sciencespo.fr), Sciences Po, CEPR
- [Clément Gorin](mailto:clement.gorin@univ-paris1.fr), Pantheon-Sorbonne University
- [Shohei Nakamura](mailto:snakamura2@worldbank.org), World Bank - Poverty & Equity Global Practice
- [Mark Roberts](mailto:mroberts1@worldbank.org), World Bank - Resilience, and Land Global Practice
- [Benjamin Stewart](mailto:bstewart@worldbankgroup.org), World Bank - Geospatial Operations Support Team

**Description:** This document provides instructions on how to use the delineations (see section `Using delineations`) computed in the paper, as well as instructions to replicate the delineations (see section `Computing delineations`). All spatial datasets use the projected Coordinate Reference System World Mollweide (`ESRI:54009`) to preserves surface area. The resolution is 250m × 250m in projected space.

## 1. Using delineations

We provide the delineations computed in the paper as separate Geopackage files containing the geometries and the corresponding variables for the different types of delineation. Each type of delineation `[de]` is available for download.

### Downloads

- Urban areas: [`ur.gpkg`](https://www.dropbox.com/scl/fi/rgr4j3r0s3cw5mubg0sji/tgo_cc.gpkg?rlkey=p9jdjjm1jzl1kejvm3v6mu0a0&dl=1)  (492 KB)
- Urban cores: [`co.gpkg`](https://www.dropbox.com/scl/fi/pywdob05r20jynpqkj0i2/tgo_co.gpkg?rlkey=0cf4aeet8jppkpdsv9triapzk&dl=1) (131KB)
- Cities: [`cc.gpkg`](https://www.dropbox.com/scl/fi/rgr4j3r0s3cw5mubg0sji/tgo_cc.gpkg?rlkey=p9jdjjm1jzl1kejvm3v6mu0a0&dl=1) (172 KB)
- Urban centres: [`ce.gpkg`](https://www.dropbox.com/scl/fi/pa35r1a3gzb01v9noa7ch/tgo_ce.gpkg?rlkey=glk85pqgdjuq6vpjllyrevs2c&dl=1) (131 KB)

### Variable descriptions

| Variable                     | Description                         |
|------------------------------|-------------------------------------|
| `decpo15d10b5000_[de]`       | Delineation identifier              |
| `country`                    | Country ISO                         |
| `namecpo15d10b5000_[de]`     | Delineation name (when available)   |
| `typecpo15d10b5000_[de]`     | Type of place (city, town, village) |
| `aredcpo15d10b5000_[de]d`    | Delineation area                    |
| `cpo15dcpo15d10b5000_[de]d`  | [Description]                       |
| `dcpo15dcpo15d10b5000_[de]d` | [Description]                       |
| `gbudcpo15d10b5000_[de]d`    | [Description]                       |
| `dgbudcpo15d10b5000_[de]d`   | [Description]                       |

## 2. Computing delineations

We provide the input data used to compute the delineations, along with the various Stata datasets referenced in the paper. This allows users to reproduce the delineations potentially with different parameter settings. See this [repository](https://github.com/goclem/delineation) for the corresponding scripts and parameter description. 

### Downloads

| Country                  | Rasters                | Datasets               |
|--------------------------|------------------------|------------------------|
| Angola                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Benin                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Botswana                 | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Burkina Faso             | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Burundi                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Cameroon                 | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Cape Verde               | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Central African R.       | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Chad                     | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Comoros                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Congo Brazzaville        | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Congo RDC                | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Côte d'Ivoire            | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Eritrea                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Ethiopia                 | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Gabon                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Gambia                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Ghana                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Guinea                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Guinea-Bissau            | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Kenya                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Lesotho                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Liberia                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Madagascar               | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Malawi                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Mali                     | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Mauritania               | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Mauritius                | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Mozambique               | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Namibia                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Niger                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Nigeria                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Rwanda                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Sao Tome and Principe    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Senegal                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Seychelles               | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Sierra Leone             | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Somalia                  | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| South Africa             | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| South Sudan              | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Sudan                    | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Swaziland                | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Tanzania                 | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Togo                     | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Uganda                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Zambia                   | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|
| Zimbabwe                 | [Rasters](#) (`size`)  | [Datasets](#) (`size`)|

### Input data

| File name        | Description                                       | Raster | Dataset |
|------------------|---------------------------------------------------|--------|---------|
| `[co]_ids`       | Unique pixel identifiers                          | Yes    | Yes     |
| `[co]_cpo15`     | Cell population                                   | Yes    | Yes     |
| `[co]_gbu`       | Share of built-up area (% x 100)                  | Yes    | Yes     |
| `[co]_elevation` | Average pixel elevation (metres)                  | Yes    | Yes     |
| `[co]_slope`     | Average pixel slope (% x 100)                     | Yes    | Yes     |
| `[co]_water`     | Pixel within a water area (binary)                | Yes    | Yes     |
| `[co]_desert`    | Pixel within a desert area (binary)               | Yes    | Yes     |    

**File names:** `[co]_[variable]`

- `[co]`: Country code
- `[variable]`: See table below

### Unlivable data

| File name                 | Description                                                 | Raster | Dataset |
|---------------------------|-------------------------------------------------------------|--------|---------|
| `[co]_unlcpo15_all`       | Pixels classified as unlivable under any criterion (binary) | Yes    | No      |     
| `[co]_unlcpo15_crit1`     | Unlivable pixels based on water (binary)                    | Yes    | No      |
| `[co]_unlcpo15_crit2`     | Unlivable pixels based on slope (binary)                    | Yes    | No      |
| `[co]_unlcpo15_crit3`     | Unlivable pixels based on desert (binary)                   | Yes    | No      |

**File names:** `[co]_unl[density]_[variable]`

- `[co]`: Country code
- `[density]`: Density used for the delineations (e.g. `cpo15`)
- `[variable]`: See table below

### Delineation data

| File name               | Description                                         | Raster | Dataset |
|-------------------------|-----------------------------------------------------|--------|---------|
| `[co]_cpo15d10b5000_ur` | Urban area (`ur` identifier)                        | Yes    | Yes     |
| `[co]_cpo15d10b5000_co` | Urban core (`co` identifier)                        | Yes    | Yes     |
| `[co]_cpo15d10b5000_cc` | Cities – Urban area with a core (`ur` identifier)   | Yes    | Yes     |
| `[co]_cpo15d10b5000_to` | Towns – Urban area without a core (`ur` identifier) | Yes    | Yes     |
| `[co]_cpo15d10b5000_ce` | Urban centre (`ce` identifier)                      | Yes    | Yes     |
| `[co]_cpo15d10b5000_ct` | Urban core threshold                                | Yes    | Yes     |
| `[co]_cpo15d10b5000_ut` | Urban area threshold                                | Yes    | Yes     |
| `[co]_cpo15d10b5000_et` | Urban centre threshold                              | Yes    | Yes     |

**File names:** `[co]_[density]d[bandwidth]b[bootstraps]_[type]`
	
- `[co]`: Country code
- `[density]`: Density used for the delineations (e.g. `cpo15`)
- `[bandwidth]`: Kernel bandwidth (e.g. `d10`)
- `[bootstaps]`: Number of bootstraps (e.g. `b5000`)
- `[type]`: Delineation or threshold. See table below

### Other datasets

- `[co]_bpi.dta`: Source dataset (country-level source data)
- `[co]_bco.dta`: Aggregated source dataset
- `[co]_ids_lalo.dta`: Pixel coordinates
- `[co]_desdelb5000.dta`: Descriptive statistics of delineated units
- `[co]_Zipfd10b5000.dta`: Zipf's Law computation
- `[co]_statce.dta`: Descriptive statistics on city centres
- `[co]_statgrcpo15d10b5000_cc.dta`: Descriptive statistics on within-city gradient
- Datasets for gradient regression
	- `[co]_bregracpo15cpo15d10b5000_cc.dta`
	- `[co]_bregracpo15d10b5000_cc.dta`

# Questions

- Raster formatting: We can get the raster to use 5-6 times less space by using an integer data type (e.g. `UInt8` or `UInt16`) and compression (e.g. LZW). No data values are inconsistent across rasters.
- Dataset formatting: Stata datasets should also be compressed
- Datasets should be renamed to match the raster names
- Are `[co]_water.tif` and `[co]_desert.tif` binary for other countries?
- Do we want to share all variables in the `Using delineations` section? 
- Should we detail the variables of the `Descriptive statistics` section?
