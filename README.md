# Data package

**Paper**: [An Anatomy of Urbanization in Sub-Saharan Africa](https://documents1.worldbank.org/curated/en/099415311272320571/pdf/IDU0faef6c000aaba0485209f0e08928760d9a57.pdf)

**Authors:**

- [Pierre-Philippe Combes](mailto:pierrephilippe.combes@sciencespo.fr), Sciences Po, CEPR
- [Clément Gorin](mailto:clement.gorin@univ-paris1.fr), Pantheon-Sorbonne University
- [Shohei Nakamura](mailto:snakamura2@worldbank.org), World Bank - Poverty & Equity Global Practice
- [Mark Roberts](mailto:mroberts1@worldbank.org), World Bank - Resilience, and Land Global Practice
- [Benjamin Stewart](mailto:bstewart@worldbankgroup.org), World Bank - Geospatial Operations Support Team

**Description:** This document provides instructions on how to use the delineations (see section `Using delineations`) computed in the paper, as well as instructions to replicate the delineations (see section `Replicating delineations`).

## Using delineations

We provide the delineations computed in the paper as a Geopackage file containing the geometries and the corresponding variables for the different types of delineation, each stored in a separate layer. All spatial datasets use the projected Coordinate Reference System World Mollweide (`ESRI:54009`) to preserves surface area. The resolution is 250m × 250m in projected space.

- File: `./Geometries/delineations.gpkg`
- Delineation layers `[de]`:
	- Urban areas `ur`
	- Urban cores `co`
	- Cities - Urban areas with a core `cc`
	- Urban centres `ce`
- Variables:
	- For each layer except `ce`

| Variable                     | Description                         | Type        |
|------------------------------|-------------------------------------|-------------|
| `decpo15d10b5000_[de]`       | Delineation identifier              | `Integer`   |
| `country`                    | Country ISO                         | `Character` |
| `namecpo15d10b5000_[de]`     | Delineation name (when available)   | `Character` |
| `typecpo15d10b5000_[de]`     | Type of place (city, town, village) | `Character` |
| `aredcpo15d10b5000_[de]d`    | Delineation area                    | `[Type]`    |
| `cpo15dcpo15d10b5000_[de]d`  | [Description]                       | `[Type]`    |
| `dcpo15dcpo15d10b5000_[de]d` | [Description]                       | `[Type]`    |
| `gbudcpo15d10b5000_[de]d`    | [Description]                       | `[Type]`    |
| `dgbudcpo15d10b5000_[de]d`   | [Description]                       | `[Type]`    |

## Replicating delineations

### Inputs

- Files: `./Inputs/[co]_[variable].tif`
	- `[co]`: Country code
	- `[variable]`: See table below

| File name            | Description                                       | Data type |
|----------------------|---------------------------------------------------|-----------|
| `[co]_ids.tif`       | Unique pixel identifiers                          | `UInt32`  |
| `[co]_cpo15.tif`     | Cell population                                   | `Float32` |
| `[co]_gbu.tif`       | Share of built-up area (% x 100)                  | `Float32` |
| `[co]_elevation.tif` | Average pixel elevation (metres)                  | `Float32` |
| `[co]_slope.tif`     | Average pixel slope (% x 100)                     | `Float32` |
| `[co]_water.tif`     | Pixel within a water area (binary)                | `Float32` |
| `[co]_desert.tif`    | Pixel within a desert area (binary)               | `Float32` |         

### Outputs

#### Unlivable rasters

- Files: `./Rasters/[co]_unl[density]_[type].tif`
	- `[co]`: Country code
	- `[density]`: Density used for the delineations (e.g. `cpo15`)
	- `[type]`: Type of unlivable area (e.g. `crit1`)

| File name                 | Description                                                 | Data type |
|---------------------------|-------------------------------------------------------------|-----------|
| `[co]_unlcpo15_all.tif`   | Pixels classified as unlivable under any criterion (binary) | `Float32` |
| `[co]_unlcpo15_crit1.tif` | Unlivable pixels based on water (binary)                    | `Float32` |
| `[co]_unlcpo15_crit2.tif` | Unlivable pixels based on slope (binary)                    | `Float32` |
| `[co]_unlcpo15_crit3.tif` | Unlivable pixels based on desert (binary)                   | `Float32` |

#### Delineation rasters

- Files: `./Delineations/[co]_[density]d[bandwidth]b[bootstraps]_[type].tif`
	- `[co]`: Country code
	- `[density]`: Density used for the delineations (e.g. `cpo15`)
	- `[bandwidth]`: Kernel bandwidth (e.g. `d10`)
	- `[bootstaps]`: Number of bootstraps (e.g. `b5000`)
	- `[type]`: Delineation or threshold. See table below

| File Name                   | Description                                         | Data Type |
|-----------------------------|-----------------------------------------------------|-----------|
| `[co]_cpo15d10b5000_ur.tif` | Urban area (`ur` identifier)                        | `Float32` |
| `[co]_cpo15d10b5000_co.tif` | Urban core (`co` identifier)                        | `Float32` |
| `[co]_cpo15d10b5000_ce.tif` | Urban centre (`ce` identifier)                      | `Float32` |
| `[co]_cpo15d10b5000_cc.tif` | Cities - Urban area with a core (`ur` identifier)   | `Float32` |
| `[co]_cpo15d10b5000_to.tif` | Towns - Urban area without a core (`ur` identifier) | `Float32` |
| `[co]_cpo15d10b5000_ct.tif` | Urban core threshold                                | `Float32` |
| `[co]_cpo15d10b5000_ut.tif` | Urban area threshold                                | `Float32` |
| `[co]_cpo15d10b5000_et.tif` | Urban centre threshold                              | `Float32` |

#### Stata Datasets 

- Source dataset: `[co]_bpi.dta` (country-level source data)
- Aggregated source dataset: `[co]_bco.dta`
- Pixel coordinates: `[co]_ids_lalo.dta`
- 6 source datasets (e.g., `cpo15`, `gbu`, `elevation`, etc.)
- 5 datasets by delineated units:  
  `[co]_bdecpo15d10b5000_tt.dta` (tt = `ur`, `co`, `cc`, `to`, `ce`)  
  Includes:
  - `deold`: identifier on TIFF files (area rank)
  - `de`: identifier in Stata (population rank)
- 5 datasets with pixel-unit identifiers:  
  `[co]_cpo15d10b5000_tt.dta` (same `tt` values)  
  Also includes `deold` and `de` variables
- 2 large datasets for gradient regressions:  
   `[co]_bregracpo15cpo15d10b5000_cc`  
  Includes all fixed effects and interacted distance terms.  
  (Consider creating a smaller version with only city-centre distance and minimal dummies)

#### Descriptive Statistics

- `[co]_desdelb5000.dta`: Descriptive statistics of delineated units
- `[co]_Zipfd10b5000.dta`: Zipf's Law computation
- `[co]_statce.dta`: Descriptive statistics on city centres
- `[co]_statgrcpo15d10b5000_cc.dta`: Descriptive statistics on within-city gradient

# Questions

- Raster formatting: We can get the raster to use 5-6 times less space by using an integer data type (e.g. `UInt8` or `UInt16`) and compression (e.g. LZW). No data values are inconsistent across rasters.
- Dataset formatting: Stata datasets should also be compressed
- Are `[co]_water.tif` and `[co]_desert.tif` binary for other countries?
- Do we want to share all variables in the `Using delineations` section? 
- Should we detail the variables of the `Descriptive statistics` section?
