# Data Dictionary

## `data/01_matched_common_timestamps/`

Each file contains a MATLAB structure named `stats`.

| Field | Description | Units |
|---|---|---|
| `name` | Tide gauge station name | none |
| `tg_id` | Tide gauge station identifier | none |
| `lonlat` | Longitude and latitude of tide gauge | degrees |
| `datapointsnum` | Number of matched hourly observations | count |
| `tg_vals` | Tide gauge nontidal residual values | meters |
| `ales_vals` | ALES satellite nontidal residual values | meters |
| `xtrk_vals` | XTRACK satellite nontidal residual values | meters |
| `cmem_vals` | CMEMS satellite nontidal residual values | meters |
| `ALES` | ALES performance/statistics structure | mixed |
| `XTRACK` | XTRACK performance/statistics structure | mixed |
| `CMEMS` | CMEMS performance/statistics structure | mixed |
| `common_times_datenum` | Common matched timestamps | MATLAB datenum |

## `data/02_product_specific_timeseries/<PRODUCT>/`

Each file contains a MATLAB structure named `stats`.

| Field | Description | Units |
|---|---|---|
| `name` | Tide gauge station name | none |
| `lonlat` | Longitude and latitude of tide gauge | degrees |
| `rmse` | Root-mean-square error between tide gauge and satellite NTR | meters |
| `pear_corr` | Pearson correlation coefficient | unitless |
| `kge` | Kling-Gupta efficiency | unitless |
| `bias` | Mean bias | meters |
| `mmi` | Modified Mielke Index | unitless |
| `datapointsnum` | Number of matched observations | count |
| `tg_vals` | Tide gauge nontidal residual values | meters |
| `sat_vals` | Satellite nontidal residual values | meters |
| `timenum` | Matched timestamps | MATLAB datenum |

## `data/03_tg_percentile_thresholds/`

Each file contains tide gauge-based percentile thresholds used to identify extreme nontidal residual values.

| Variable | Description | Units |
|---|---|---|
| `pVals` | Nontidal residual threshold magnitude | meters |
| `pctLst` | Percentile level corresponding to `pVals` | percentile rank |
| `st` | Tide gauge station name | none |
