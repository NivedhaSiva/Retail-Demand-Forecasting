# Retail Demand Forecasting

An exploratory retail sales forecasting capstone by Nivedha Sivakumar. The notebook explores sales patterns and implements regression, time-series, and neural-network approaches.

## Methods implemented

- Date feature engineering and exploratory visualizations of sales, promotions, holidays, and customer activity.
- Linear regression, decision tree regression, and random forest regression.
- Principal component analysis experiments.
- Store-level AR, MA, and ARIMA experiments, stationarity checks, and seasonal decomposition.
- LSTM and dense neural-network experiments using Keras.
- RMSE, MAE, and cross-validation calculations.

The presence of an import does not mean that algorithm was trained. For example, XGBoost is imported in the original notebook but is not listed here as a completed model comparison.

## Files and data

- `retail_demand_forecasting.ipynb`: original computational cells, with saved outputs and nonessential metadata removed for public sharing.
- `requirements.txt`: package names referenced by the notebook; this is not a tested environment lockfile.

The original input files are `train_data.csv`, `test_data.csv`, and `test_data_hidden.csv`. Place authorized local copies beside the notebook. They are excluded from this repository. Dataset redistribution rights and the original download source have not been established. This is the saved retail demand capstone; it has not been identified as the missing Walmart project.

## Execution status

This is a historical Python 3.9.7 notebook, preserved as an exploration rather than a production forecasting system. It has not been rerun during repository preparation. No independently validated accuracy or business-impact claim is made.

Several APIs require migration before use with current libraries: `statsmodels.tsa.arima_model.ARIMA`, `pd.datetime`, the `freq` argument to seasonal decomposition, and `keras.wrappers.scikit_learn`. Seaborn `distplot` is also legacy. Package versions from the original environment were not saved.

To reproduce, restore the input files, create an isolated Python environment, install and reconcile dependencies, select the corresponding Jupyter kernel, and run the notebook from its folder. An execution check after resolving compatibility issues is:

```sh
jupyter nbconvert --execute --to notebook --output retail_demand_forecasting.executed.ipynb retail_demand_forecasting.ipynb --ExecutePreprocessor.timeout=1800
```

## Interpretation limits

Some experimental scores are calculated on training data rather than a held-out set. Random splits also occur in this time-dependent dataset. The ANN section compares inverse-transformed predictions against scaled targets. These scores should not be presented as validated forecasting performance. A future revision should use chronological evaluation, consistent units, and a reproducible baseline.

## Author

Nivedha Sivakumar | [GitHub](https://github.com/NivedhaSiva) | [LinkedIn](https://linkedin.com/in/nivedhasivakumar)
