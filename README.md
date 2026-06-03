# Global Coastal Altimetry NTR Data

This repository contains curated MATLAB `.mat` files supporting the analysis in:

**Quadrado, G. P., Wahl, T., Enriquez, A. R., Nagaraj, M., Passaro, M., & Haigh, I. D.** Global Assessment of Satellite Altimetry for Observing Extreme Coastal Sea Levels. *Communications Earth & Environment*.

## Repository overview

This repository provides tide-gauge and satellite-altimetry matched non-tidal residual (NTR) datasets used to evaluate the skill of coastal satellite altimetry products in observing extreme coastal sea levels.

The curated data include:

- matched common-timestamp files across ALES, XTRACK, and CMEMS;
- product-specific tide-gauge/satellite matched time series for CMEMS, XTRACK, and ALES;
- tide-gauge-based percentile thresholds used to identify extreme NTR values.

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

scripts/
```

## Data folders

### `data/01_matched_common_timestamps/`

Individual tide-gauge files used for the direct comparison across all satellite altimetry products using common matched timestamps.

Each file contains a MATLAB structure named `stats`, including tide-gauge NTR values, satellite NTR values from ALES, XTRACK, and CMEMS, and common matched timestamps.

### `data/02_product_specific_timeseries/`

Individual tide-gauge files for product-specific analyses. Files are organized by product:

- `CMEMS`
- `XTRACK`
- `ALES`

Each file contains a MATLAB structure named `stats`, including tide-gauge NTR values, satellite NTR values, matched timestamps, and performance metrics.

### `data/03_tg_percentile_thresholds/`

Individual tide-gauge files containing percentile thresholds used to identify extreme NTR values.

Each file contains:

- `pVals`: NTR threshold magnitudes in meters;
- `pctLst`: percentile levels;
- `st`: tide-gauge station name.

## Excluded tide gauges

Problematic tide gauges identified during quality control were removed from the curated datasets.

## Documentation

A data dictionary describing file contents and variables is provided in:

`docs/DATA_DICTIONARY.md`

## Software

The MATLAB scripts used to curate and check the repository are provided in `scripts/`.

## Citation

Please cite the associated paper and the archived Zenodo version of this repository when using these data.

## License

License information will be added before public release.
