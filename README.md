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
      
      
  1. **silent [Default: 0]** – if set to 1, no running messages will be printed. Yet these messages can be helpful sometimes.
  
  1. **nthread [Default is set to the maximum number of threads available]** – used for parallel processing. If you wish to run on all cores, then the number need not to be added. The algorithm detects it itself. Otherwise add the necessary number of cores.

### 1. Booster Parameters
As mentioned above, there are 2 boosters in the model. Yet, the most used booster is gbtree as it always outperforms gblinear. Therefore, only gbtree is described here.

  1. **learning_rate [Default: 0.3]** – makes the model more vigorous by shrinking the weights on each step. Typical values lie between 0.01-0.03.
  
  1. **min-child-weight [Default: 1]** – minimum sum of instance weight required in a child. Used to control overfitting. Higher values can prevent the model from learning relations that might be highly specific to a particular sample. Yet too high values will cause underfitting. Should be tuned using Cross Validation (CV).
  
  1. **max_depth [Default: 6]** – maximum depth of a tree. Higher values may cause overfitting. Hence should be tuned using CV.
  
  1. **max_lead_nodes** – maximum number of leaves in a tree. Can be defined instead of max_depth as binary trees are created.
  
  1. **gamma [Default: 0]** – indicates the minimum lost reduction required to make a new split in a tree. The values can vary depending on the loss function used.
  
  1. **subsample [Default: 1]** – indicates the fraction of samples required to be randomly sampled for each tree. Lower values prevent the model from overfitting yet can cause underfitting. 
  
  1. **colsample_bytree [Default: 1]** – indicates the fraction of columns to be randomly used in each tree. Typical values fall between 0.5-1.
  
  1. **colsample_bylevel [Default: 1]** – indicates the subsample ration of columns for each level. Rarely used if subsample and colsample_bytree is specified.
  
  1. **reg_lambda [Default: 1]** – L2 regularization term on weights. This constant is used for regularization.
  
  1. **reg_alpha [Default: 1]** – L1 regularization term on weights. In case of a very high dimensionality problem this constant can be used to run the algorithm faster.
  
  1. **scale_pos_weight [Default: 1]** – in case of high class imbalance, a value greater than 0 should be used for faster convergence.















