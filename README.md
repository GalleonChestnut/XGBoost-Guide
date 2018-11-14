# Guide to use XGBoost Model
These articles try to cover the hyper parameter tuning part in the XGBoost model

## What is XGboost?
XGBoost has recently become a popular algorithm in applied machine learning and Kaggle competitions. The model’s efficiency in computational time and usage of memory resources has built-up its reputation. Gradient boosting decision tree algorithm is used as the underlying concept of XGBoost.

![Image of Comparing several models](/XGBoost_Guide/Benchmark-Performance-of-XGBoost.png)
###### Benchmark Performance of XGBoost, taken from [Benchmarking RandomForest Implementations](http://datascience.la/benchmarking-random-forest-implementations/) XGBoost is almost all the time faster than other models

The said algorithm is an ensemble technique which adds new models to minimize the errors made by the existing models up to the point where no improvements can be done any more.

## Hyper parameters of the model
XGBoost model consists of several hyper parameters that need to be tuned properly in order to achieve better performance. According to the authors of the model, these hyper parameters can be divided into 3 categories.
1. **General parameters**: corresponds to the overall functioning. Related to which booster to use in our model
1. **Booster parameters**: Guides individual boosters (trees/regression) at each step. Depends on the choice made in general parameters.
1. **Learning task parameters**: Guides the optimization process.

### 1. General Parameters
These parameters guide the overall functionality of the model. The main 3 parameters are described below. The other 2 parameters are automatically set by the model itself.
  1. **booster [Default: gbtree]** – the booster to be used at each iteration. 2 main options are available. ‘dart’ is the third option, yet it is rarely used.
    * gbtree: tree based models
    * gblinear: linear models



