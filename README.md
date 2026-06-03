# Global Satellite Altimetry Nontidal Residual (NTR) Data Release

This repository contains derived datasets supporting the analysis in:

**Quadrado, G. P., Wahl, T., Enriquez, A. R., Nagaraj, M., Passaro, M., & Haigh, I. D.** Global Assessment of Satellite Altimetry for Observing Extreme Coastal Sea Levels. *Communications Earth & Environment*.

## Repository Overview

This data release provides tide gauge–satellite altimetry matched nontidal residual (NTR) datasets used to evaluate the ability of along-track satellite altimetry products to reproduce tide gauge-derived nontidal residual variability along global coastlines.

The datasets include satellite-derived nontidal residual (NTRSAT) time series from three altimetry products:

* Copernicus Marine Service L3 Sea Surface Heights (CMEMS) 
* X-TRACK L2P v2.2 Sea Level Anomaly (X-TRACK)
* Adaptive Leading Edge Subwaveform Sea Surface Heights v56 (ALES)

The data release includes:

* common-timestamp NTRTG–NTRSAT files used for direct comparison across CMEMS, X-TRACK, and ALES;
* product-specific NTRTG–NTRSAT matched time series used for analyses that do not require common timestamps across products;
* tide gauge-based NTRTG percentile thresholds used to identify extreme nontidal residual values.

## Repository Structure

```text
data/
├── 01_matched_common_timestamps/
├── 02_product_specific_timeseries/
│   ├── CMEMS/
│   ├── XTRACK/
│   └── ALES/
└── 03_tg_percentile_thresholds/

docs/
└── DATA_DICTIONARY.md
```

## Dataset Descriptions

### Common-timestamp product comparison files

[`data/01_matched_common_timestamps/`](data/01_matched_common_timestamps/) contains individual tide gauge site-level `.mat` files used for direct comparison of CMEMS, X-TRACK, and ALES. Each file includes matched tide gauge-derived nontidal residuals (`NTRTG`) and satellite-derived nontidal residuals (`NTRSAT`) from all three products at common coincident timestamps.

These files are intended for analyses where all three satellite altimetry products are compared using the same tide gauge sites and the same matched times.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* `NTRTG` values from the tide gauge record;
* `NTRSAT` values from ALES, X-TRACK, and CMEMS;
* common timestamps shared by the tide gauge record and all three satellite products;
* product-specific performance statistics.

### Product-specific matched NTR time series

[`data/02_product_specific_timeseries/`](data/02_product_specific_timeseries/) contains individual tide gauge site-level `.mat` files with matched `NTRTG–NTRSAT` time series for each satellite altimetry product. Files are organized by product: [`CMEMS`](data/02_product_specific_timeseries/CMEMS/), [`XTRACK`](data/02_product_specific_timeseries/XTRACK/), and [`ALES`](data/02_product_specific_timeseries/ALES/).

These files are intended for analyses where each satellite product is evaluated independently, without requiring common timestamps across CMEMS, X-TRACK, and ALES.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* `NTRTG` values from the tide gauge record;
* `NTRSAT` values from one satellite altimetry product;
* matched timestamps for the `NTRTG–NTRSAT` pairs;
* performance metrics, including Pearson correlation coefficient, root-mean-square error, bias, Kling-Gupta efficiency, and Modified Mielke Index.

### Tide gauge percentile thresholds

[`data/03_tg_percentile_thresholds/`](data/03_tg_percentile_thresholds/) contains individual tide gauge site-level `.mat` files with percentile thresholds computed from the empirical `NTRTG` distribution. These thresholds are used to identify extreme tide gauge-derived nontidal residual values.

Each `.mat` file contains:

* `pVals`: `NTRTG` threshold magnitudes in meters;
* `pctLst`: percentile levels;
* `st`: tide gauge station name.

Extreme `NTRTG` values are defined as hourly exceedances above these percentile thresholds.

## Documentation

A data dictionary describing the file contents, variables, and units is available here:

[`docs/DATA_DICTIONARY.md`](docs/DATA_DICTIONARY.md)

## Citation

Please cite the associated paper and the archived Zenodo version of this repository when using these datasets.

The Zenodo DOI will be added after the final repository release.
