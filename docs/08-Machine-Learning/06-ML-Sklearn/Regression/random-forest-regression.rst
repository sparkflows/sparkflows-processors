Sklearn Random Forest Regression
=========== 

Random Forest Regression, fits a number of classifying decision trees on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. The sub-sample size is controlled with the max_samples parameter if bootstrap=True (default), otherwise the whole dataset is used to build each tree.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnRandomForestRegression

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
      * - n_estimators
        - Number of Estimators
        - Specifies the number of trees in the forest.
      * - criterion
        - Criterion
        - The function to measure the quality of a split.
      * - max_depth
        - Max Depth
        - The maximum depth of the tree. If not set, nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples.
      * - min_samples_split
        - Min Samples Split
        - The minimum number of samples required to split an internal node. Higher values prevent a tree from growing too complex.
      * - min_samples_leaf
        - Min Samples Leaf
        - The minimum number of samples required to be at a leaf node.
      * - min_weight_fraction_leaf
        - Min Weight Fraction Leaf
        - The minimum weighted fraction of the sum total of weights required to be at a leaf node.
      * - max_features
        - Max Features
        - The number of features to consider when looking for the best split.
      * - max_leaf_nodes
        - Max Leaf Nodes
        - Grow trees with max_leaf_nodes in best-first fashion. If not set, then unlimited number of leaf nodes.
      * - min_impurity_decrease
        - Min Impurity Decrease
        - A threshold for early stopping in tree growth. A node will split if its impurity is above the threshold, otherwise it is a leaf.
      * - min_impurity_split
        - Min Impurity Split
        - Threshold for early stopping in tree growth, a node will split if its impurity is above the threshold.
      * - bootstrap
        - Bootstrap
        - Whether bootstrap samples are used when building trees.
      * - oob_score
        - Oob Score
        - Whether to use out-of-bag samples to estimate the R^2 on unseen data.
      * - random_state
        - Random State
        - Controls the randomness of the bootstrapping of the samples used when building trees (if bootstrap=True). Default value is None
      * - warm_start
        - Warm Start
        - When warm_start is true, the existing fitted model attributes an are used to initialise the new model in a subsequent call to fit.


Details
-------


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html


