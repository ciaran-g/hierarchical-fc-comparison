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
