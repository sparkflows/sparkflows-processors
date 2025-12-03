Feature Selection
===========

Compute per-feature importance for classification, regression, or clustering. Supports linear/logistic (|coefficients|), RandomForest/GBT (impurity importances), and KMeans (CH-style score per feature) with optional scaling.

Input
--------------
Takes a Spark DataFrame as input.

Output
--------------
Spark DataFrame of feature rankings with columns: feature, model_importance, std_unscaled, ch_feature, scaling_used.

Type
--------- 

transform

Class
--------- 

fire.nodes.fe.NodeFeatureImportance

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - modelType
        - Model Type
        - Choose task type. Label is required for classification/regression.
      * - modelName
        - Model
        - Estimator used to derive importances. For classification use logistic_regression/random_forest/gbt; for regression use linear_regression/random_forest/gbt; for clustering use kmeans.
      * - label
        - Label Column
        - Required for classification/regression.
      * - features
        - Feature Columns
        - Numeric feature columns used for importance computation.
      * - nClusters
        - Number of Clusters (k)
        - Used only when Model Type = clustering (k-means).
      * - scaling
        - Scaling
        - Optional scaling applied before modeling. Unscaled stats are always computed from original columns.
      * - topK
        - Top K Rows
        - Limit output to top K rows (0 = no limit).




