# Retail Demand Forecasting

Revised ML learning project by Nivedha Sivakumar, using calendar and scheduled retail features.

## Repairs
- Chronological expanding-window validation for April, May, and June 2015; one separate July holdout after model selection.
- Exclude contemporaneous customer counts. Fit preprocessing on training windows only.
- Compare seasonal-naive, linear regression, decision tree and random forest; report MAE, RMSE, and WAPE on original sales units.
- Fixed, evenly spaced 30-store cohort chosen from IDs only; set `STORE_LIMIT=None` for all stores. Results are cohort-specific.
- Replace obsolete APIs and legacy ARIMA/ANN/LSTM/PCA experiments with a coherent ML evaluation. The original notebook remains in Git history.

## Reproduce
Python 3.12: `pip install -r requirements.txt`. Place authorized `train_data.csv`, `test_data.csv`, and `test_data_hidden.csv` in `data/`. Run `retail_demand_forecasting.ipynb` top-to-bottom. Test dates are parsed explicitly in their supplied formats. Scheduled opening, promotion, and holiday features are assumed known for the forecast horizon.

Executed successfully top-to-bottom on the local source data using Python 3.12. Exact tested package versions are recorded in requirements-lock.txt. All six saved figures across the two retail projects were visually reviewed. Direct package versions are pinned in requirements.txt; requirements-lock.txt records the full shared review environment (including packages unused by this project).

## Limits
Historical one-month evaluation on a fixed cohort does not establish full-chain or current performance. Course-file provenance and redistribution rights are unverified. Data is not published. This has not been identified as the missing Walmart project.

## Executed results

Expanding-window validation selected linear regression. The July 2015 holdout contains 930 store-days across 30 preselected stores. Holdout MAE: 791.19; RMSE: 1113.01 sales units; WAPE: 12.57%. Seasonal-naive WAPE: 24.35%. These are historical cohort results, not full-chain or current performance.

Machine-readable aggregate results are in `results.json`; source data and customer-level predictions are excluded.
