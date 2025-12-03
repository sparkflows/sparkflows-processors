Sklearn XGBoost Regressor
=========== 

XGBoost Regressor for regression tasks. It implements gradient boosted decision trees designed for speed and performance.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeXGBoostRegressor

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - targetCol
        - Target Column
        - The label column for model fitting
      * - featureCols
        - Feature Columns
        - Feature columns of type - all numeric, boolean and vector
      * - splitRatio
        - Split Ratio
        - Split Ratio
      * - n_estimators
        - Number of Estimators
        - Number of boosting rounds (trees).
      * - max_depth
        - Max Depth
        - Maximum depth of a tree. Increasing makes model more complex.
      * - learning_rate
        - Learning Rate
        - Boosting learning rate (xgb's eta).
      * - subsample
        - Subsample
        - Subsample ratio of the training instance.
      * - colsample_bytree
        - Colsample Bytree
        - Subsample ratio of columns when constructing each tree.
      * - colsample_bylevel
        - Colsample Bylevel
        - Subsample ratio of columns for each split, in each level.
      * - colsample_bynode
        - Colsample Bynode
        - Subsample ratio of columns for each split, in each node.
      * - reg_alpha
        - Reg Alpha (L1)
        - L1 regularization term on weights.
      * - reg_lambda
        - Reg Lambda (L2)
        - L2 regularization term on weights.
      * - gamma
        - Gamma
        - Minimum loss reduction required to make a further partition on a leaf node.
      * - min_child_weight
        - Min Child Weight
        - Minimum sum of instance weight needed in a child.
      * - max_delta_step
        - Max Delta Step
        - Maximum delta step allowed for each tree’s weight estimation.
      * - random_state
        - Random State
        - Random number seed.
      * - n_jobs
        - Number of Jobs
        - Number of parallel threads used to run xgboost.
      * - verbosity
        - Verbosity
        - Verbosity of printing messages (0 = silent, 1 = warning, 2 = info, 3 = debug).
      * - booster
        - Booster
        - Specify which booster to use.
      * - tree_method
        - Tree Method
        - Tree construction algorithm used in XGBoost.
      * - objective
        - Objective
        - Learning task and objective function.
      * - eval_metric
        - Evaluation Metric
        - Evaluation metric for validation data.
      * - early_stopping_rounds
        - Early Stopping Rounds
        - Activates early stopping. Validation metric needs to improve at least once in every given rounds.


Details
-------
More details are available at : https://xgboost.readthedocs.io/en/stable/python/python_api.html#xgboost.XGBRegressor


