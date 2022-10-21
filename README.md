# sktime-fable-hierarchical forecasting experiement

Here the plan is to use both a real world dataset (labour) and a synethic data set to compare the hierachical forecasting results from sktime (python) and fable (R).

The goal is to make sure the sktime implementation is consistent with the fable one. Therefore we will us a simple and consistent base forecaster across python and R.


#### Environment
```
conda create -n sktime_hier python=3.7 -y
conda activate sktime_hier
pip install sktime
pip install datasetsforecast
pip install requests
pip install statsforecast
conda install ipykernel -y
```

#### Results

The forecasts are evaluated using RMSE.

| Synthetic dataset                         |
| Model          | Sktime      | Fable      |
|----------------|-------------|------------|
| base           |  2601.781   | 2601.781   |
| bu             |  2601.857   | 2601.857   |
| mint_cov       |  496458.562*| -          |
| mint_shrink    |  2601.781   | 2601.829   |
| ols            |  2601.781   | 2601.781   |
| td_fcst        |  2601.771   | -          |
| wls_str        |  2601.776   | 2601.800   |
| wls_var        |  2601.776   | 2601.800   |
