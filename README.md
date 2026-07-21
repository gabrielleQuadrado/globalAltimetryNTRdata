# Global Tide Gauge-Satellite Altimetry Nontidal Residual (NTR) Data Release
[![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20543274-blue)](https://doi.org/10.5281/zenodo.20543274)

This repository contains derived datasets used in the analyses in:

**Quadrado, G. P., Wahl, T., Enriquez, A. R., Nagaraj, M., Passaro, M., & Haigh, I. D.** 	Can Satellite Altimetry Observe Extreme Coastal Sea Levels? A Global Evaluation Across Products and Coastal Settings. Submitted to *Journal of Geophysical Research: Oceans*.

## Repository Overview

This data release provides tide gauge–satellite altimetry matched nontidal residual (NTR) datasets used to evaluate the ability of along-track satellite altimetry products to reproduce tide gauge-derived nontidal residual variability (NTR<sub>TG</sub>) along global coastlines.

The datasets include satellite-derived nontidal residual (NTR<sub>SAT</sub>) time series from three altimetry products:

* Copernicus Marine Service L3 Sea Surface Heights (CMEMS)
* X-TRACK L2P v2.2 Sea Level Anomaly (X-TRACK)
* Adaptive Leading Edge Subwaveform Sea Surface Heights v56 (ALES)

The data release includes:

* common-timestamp NTR<sub>TG</sub>–NTR<sub>SAT</sub> files used for direct comparison across CMEMS, X-TRACK, and ALES;
* product-specific NTR<sub>TG</sub>–NTR<sub>SAT</sub> matched time series used for analyses that do not require common timestamps across products;
* tide gauge-based NTR<sub>TG</sub> percentile thresholds used to identify extreme nontidal residual values.

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

### Common-Timestamp Matched NTR<sub>TG</sub>–NTR<sub>SAT</sub> Time Series

[`data/01_matched_common_timestamps/`](data/01_matched_common_timestamps/) contains individual tide gauge site-level `.mat` files used for direct comparison of CMEMS, X-TRACK, and ALES. Each file includes matched tide gauge-derived nontidal residuals (NTR<sub>TG</sub>) and satellite-derived nontidal residuals (NTR<sub>SAT</sub>) time series from all three products at common coincident timestamps.

These files are intended for analyses where all three satellite altimetry products are compared using the same tide gauge sites and the same matched times.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* NTR<sub>TG</sub> values from the tide gauge record in meters;
* NTR<sub>SAT</sub> values from ALES, X-TRACK, and CMEMS in meters;
* common timestamps shared by the tide gauge record and all three satellite products;
* product-specific performance statistics.

### Product-Specific Matched NTR<sub>TG</sub>–NTR<sub>SAT</sub> Time Series

[`data/02_product_specific_timeseries/`](data/02_product_specific_timeseries/) contains individual tide gauge site-level `.mat` files with matched NTR<sub>TG</sub>–NTR<sub>SAT</sub> time series for each satellite altimetry product. Files are organized by product: [`CMEMS`](data/02_product_specific_timeseries/CMEMS/), [`XTRACK`](data/02_product_specific_timeseries/XTRACK/), and [`ALES`](data/02_product_specific_timeseries/ALES/).

These files are intended for analyses where each satellite product is evaluated independently, without requiring common timestamps across CMEMS, X-TRACK, and ALES.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* NTR<sub>TG</sub> values from the tide gauge record in meters;
* NTR<sub>SAT</sub> values from one satellite altimetry product in meters;
* matched timestamps for the NTR<sub>TG</sub>–NTR<sub>SAT</sub> pairs;
* performance metrics, including Pearson correlation coefficient, root-mean-square error, bias, Kling-Gupta efficiency, and Modified Mielke Index.

### Tide Gauge Percentile Thresholds

[`data/03_tg_percentile_thresholds/`](data/03_tg_percentile_thresholds/) contains individual tide gauge site-level `.mat` files with percentile thresholds computed from the empirical NTR<sub>TG</sub> distribution. These thresholds are used to identify extreme tide gauge-derived nontidal residual values.

Each `.mat` file contains:

* `pVals`: NTR<sub>TG</sub> threshold magnitudes in meters;
* `pctLst`: percentile ranks corresponding to `pVals`;
* `st`: tide gauge station name.

Extreme NTR<sub>TG</sub> values are defined as hourly exceedances above these percentile thresholds.

## Documentation

A data dictionary describing the file contents, variables, and units is available here:

[`docs/DATA_DICTIONARY.md`](docs/DATA_DICTIONARY.md)

## Citation

Please cite the associated paper and the archived Zenodo version of this repository when using these datasets.

Archived data release: https://doi.org/10.5281/zenodo.20543274
