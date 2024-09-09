Sklearn Gradient Boosting Regression
=========== 

Gradient Boosting Regression, builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary differentiable loss functions. In each stage a regression tree is fit on the negative gradient of the given loss function.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnGradientBoostingRegressor

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
      * - loss
        - Loss
        - The loss function to be optimized. 'ls' refers to least squares regression.
      * - learning_rate
        - Learning Rate
        - Learning rate shrinks the contribution of each tree by learning_rate.
      * - n_estimators
        - Number of Estimators
        - The number of boosting stages to be run.
      * - subsample
        - Subsample
        - The fraction of samples to be used for fitting the individual base learners.
      * - criterion
        - Criterion
        - The function to measure the quality of a split.
      * - min_samples_split
        - Min Samples Split
        - The minimum number of samples required to split an internal node.
      * - min_samples_leaf
        - Min Samples Leaf
        - The minimum number of samples required to be at a leaf node.
      * - min_weight_fraction_leaf
        - Min Weight Fraction Leaf
        - The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node.
      * - max_depth
        - Max Depth
        - Maximum depth of the individual regression estimators.
      * - min_impurity_decrease
        - Min Impurity Decrease
        - A node will be split if this split induces a decrease of the impurity greater than or equal to this value.
      * - min_impurity_split
        - Min Impurity Split
        - Threshold for early stopping in tree growth. A node will split if its impurity is above the threshold.
      * - random_state
        - Random State
        - Controls the randomness of the bootstrapping of the samples used when building trees.
      * - alpha
        - Alpha
        - The alpha-quantile of the huber loss function and the quantile loss function.
      * - verbose
        - Verbose
        - Enable verbose output. If 1 then it prints progress and performance once in a while.
      * - max_leaf_nodes
        - Max Leaf Nodes
        - Grow trees with `max_leaf_nodes` in best-first fashion. If not set, then unlimited number of leaf nodes.
      * - warm_start
        - Warm Start
        - When set to True, reuse the solution of the previous call to fit as initialization, otherwise, just erase the previous solution.
      * - presort
        - Presort
        - Whether to presort the data to speed up the finding of best splits in fitting.
      * - validation_fraction
        - Validation Fraction
        - The proportion of training data to set aside as validation set for early stopping.
      * - n_iter_no_change
        - N Iter No Change
        - Used to decide if early stopping will be used to terminate training when validation score is not improving.
      * - tol
        - Tolerance
        - Tolerance for the early stopping. When the loss or score is not improving by at least `tol` for `n_iter_no_change` iterations, training stops.


Details
-------


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingRegressor.html


