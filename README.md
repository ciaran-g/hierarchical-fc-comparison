# sktime-fable-hierarchical forecasting experiement

Here the plan is to use both a real world dataset (labour) and a synethic data set to compare the hierachical forecasting results from sktime (python) and fable (R).

The goal is to compare the sktime **hierarchical** implementation is consistent with the fable one. Therefore we will use a simple and consistent base forecaster across the two libraries.


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

Overall we can see that sktime is at least on par with fable in terms of the reconciliation methods which was our goal at the start.
There are some minor differences between the methods that use the residual covariance matrix, due to how they are calculated.
Note, results with * indicate there is probably a problem with the empricical residual covariance matrix. There is a bug in the top down reconciliation method in fable which has kindly already been reported [here](https://github.com/tidyverts/fable/issues/370) by the folks from Nixtla


#### Tourism Data Results

The forecasts are evaluated using RMSE.


| Model          | Sktime      | Fable      |
|----------------|-------------|------------|
| base           |  17.523     | 17.523     |
| bu             |  17.819     | 17.819     |
| mint_cov       |  17.519     | 92.324*    |
| mint_shrink    |  17.580     | 17.596     |
| ols            |  17.519     | 17.519     |
| td_fcst        |  17.466     | -          |
| wls_str        |  17.505     | 17.614     |
| wls_var        |  17.573     | 17.614     |


#### Synthetic Data Results

The forecasts are evaluated using RMSE.


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
