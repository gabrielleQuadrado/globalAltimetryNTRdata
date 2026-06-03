# Global Satellite Altimetry Nontidal Residual (NTR) Data Release

This repository contains derived datasets supporting the analysis in:

**Quadrado, G. P., Wahl, T., Enriquez, A. R., Nagaraj, M., Passaro, M., & Haigh, I. D.** Global Assessment of Satellite Altimetry for Observing Extreme Coastal Sea Levels. *Communications Earth & Environment*.

## Repository overview

This data release provides tide gauge–satellite altimetry matched nontidal residual (NTR) datasets used to evaluate the ability of along-track satellite altimetry products to reproduce tide gauge-derived nontidal residual variability and extremes along global coastlines.

The datasets include NTR comparisons between tide gauge-derived nontidal residuals (NTRTG) and satellite-derived nontidal residuals (NTRSAT) from three altimetry products:

* Copernicus Marine Service L3 Sea Surface Heights (CMEMS)
* X-TRACK L2P v2.2 Sea Level Anomaly (X-TRACK)
* Adaptive Leading Edge Subwaveform Sea Surface Heights v56 (ALES)

The data release includes:

* common-timestamp NTRTG–NTRSAT files used for direct comparison across CMEMS, X-TRACK, and ALES;
* product-specific NTRTG–NTRSAT matched time series used for analyses that do not require common timestamps across products;
* tide gauge-based NTRTG percentile thresholds used to identify extreme nontidal residual values.

## Repository structure

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

## Data folders

| Folder                                                                                       | Description                                                                                                                   |
| -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [`data/01_matched_common_timestamps/`](data/01_matched_common_timestamps/)                   | Tide gauge files used for direct comparison across all three satellite altimetry products using common coincident timestamps. |
| [`data/02_product_specific_timeseries/`](data/02_product_specific_timeseries/)               | Product-specific NTRTG–NTRSAT matched time series for CMEMS, X-TRACK, and ALES.                                               |
| [`data/02_product_specific_timeseries/CMEMS/`](data/02_product_specific_timeseries/CMEMS/)   | Product-specific matched files for CMEMS.                                                                                     |
| [`data/02_product_specific_timeseries/XTRACK/`](data/02_product_specific_timeseries/XTRACK/) | Product-specific matched files for X-TRACK.                                                                                   |
| [`data/02_product_specific_timeseries/ALES/`](data/02_product_specific_timeseries/ALES/)     | Product-specific matched files for ALES.                                                                                      |
| [`data/03_tg_percentile_thresholds/`](data/03_tg_percentile_thresholds/)                     | Tide gauge-based percentile thresholds used to define extreme NTRTG values.                                                   |
| [`docs/DATA_DICTIONARY.md`](docs/DATA_DICTIONARY.md)                                         | Description of file contents, variables, and units.                                                                           |

## Dataset descriptions

### Common-timestamp product comparison files

[`data/01_matched_common_timestamps/`](data/01_matched_common_timestamps/) contains individual tide gauge files used to compare CMEMS, X-TRACK, and ALES at common coincident timestamps. These files support the direct inter-product comparison of satellite altimetry performance relative to tide gauge-derived nontidal residuals.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* tide gauge-derived nontidal residuals;
* satellite-derived nontidal residuals from ALES, X-TRACK, and CMEMS;
* common timestamps shared by the tide gauge and all three satellite products;
* product-specific performance statistics.

### Product-specific matched time series

[`data/02_product_specific_timeseries/`](data/02_product_specific_timeseries/) contains product-specific NTRTG–NTRSAT matched time series. These files are organized by altimetry product and are used for analyses where each product is evaluated independently.

Each `.mat` file contains a MATLAB structure named `stats`, including:

* tide gauge-derived nontidal residuals;
* satellite-derived nontidal residuals for one altimetry product;
* matched timestamps;
* performance metrics including Pearson correlation coefficient, root-mean-square error, bias, Kling-Gupta efficiency, and Modified Mielke Index.

### Tide gauge percentile thresholds

[`data/03_tg_percentile_thresholds/`](data/03_tg_percentile_thresholds/) contains tide gauge-based percentile thresholds used to identify extreme nontidal residuals.

Each `.mat` file contains:

* `pVals`: NTRTG threshold magnitudes in meters;
* `pctLst`: percentile levels;
* `st`: tide gauge station name.

Extreme NTRTG values are defined as hourly exceedances above percentile thresholds of the empirical NTRTG distribution.

## Quality control

Problematic tide gauges identified during quality control were removed before release. The released files therefore only include tide gauge records retained for analysis after these checks.

## Documentation

A data dictionary describing the file contents, variables, and units is available here:

[`docs/DATA_DICTIONARY.md`](docs/DATA_DICTIONARY.md)

## Citation

Please cite the associated paper and the archived Zenodo version of this repository when using these datasets.

The Zenodo DOI will be added after the final repository release.
