Sklearn XGBoost Classifier
=========== 

XGBoost Classifier is an optimized gradient boosting algorithm that uses ensemble of decision trees. It is designed for efficiency, flexibility, and portability. Provides parallel tree boosting and is widely used for supervised learning tasks like classification.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeXGBoostClassifier

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
        - NEstimators
        - Number of boosting rounds (trees) to fit.
      * - max_depth
        - MaxDepth
        - Maximum depth of a tree. Increasing depth makes the model more complex and likely to overfit.
      * - learning_rate
        - LearningRate
        - Step size shrinkage used to prevent overfitting. Also called eta.
      * - subsample
        - Subsample
        - The fraction of samples used for fitting the individual base learners. Lower values help prevent overfitting.
      * - colsample_bytree
        - ColsampleByTree
        - Subsample ratio of columns when constructing each tree.
      * - gamma
        - Gamma
        - Minimum loss reduction required to make a further partition on a leaf node.
      * - min_child_weight
        - MinChildWeight
        - Minimum sum of instance weight (hessian) needed in a child.
      * - objective
        - Objective
        - Specifies the learning task and objective function.
      * - eval_metric
        - EvalMetric
        - Evaluation metric for validation data.
      * - reg_alpha
        - RegAlpha (L1)
        - L1 regularization term on weights.
      * - reg_lambda
        - RegLambda (L2)
        - L2 regularization term on weights.
      * - random_state
        - RandomState
        - Random seed for reproducibility.
      * - n_jobs
        - NJobs
        - Number of parallel threads used to run xgboost.
      * - confusionMatrix
        - Confusion Matrix
        - 
      * - output_confusion_matrix_chart
        - Output Confusion Matrix Chart
        - Whether to display confusion matrix chart.
      * - cm_chart_title
        - Confusion Matrix Chart Title
        - Title name to display in Confusion Matrix Chart
      * - cm_chart_description
        - Confusion Matrix Chart Description
        - Description to display in Confusion Matrix Chart
      * - confusionMatrixTargetLegend
        - Confusion Matrix Target Legend
        - Legend name to display for Target in Confusion Matrix
      * - confusionMatrixPredictedLabelLegend
        - Confusion Matrix PredictedLabel Legend
        - Legend name to display for Predicted Label in Confusion Matrix
      * - confusionMatrixCountLegend
        - Confusion Matrix Count Legend
        - Legend name to display for Count in Confusion Matrix
      * - path
        - Save Confusion Matrix Path
        - Save Confusion Matrix
      * - Description
        - Confusion Matrix Description
        - 
      * - confusionMatrixRowDescription
        - Confusion Matrix Outcome description
        - One can provide the business details of the outcome of the confusion matrix rows
      * - ROC Curve
        - ROC Curve
        - 
      * - output_roc_curve
        - Output ROC Curve
        - Whether to display ROC Curve chart.
      * - roc_title
        - ROC Curve Chart Title
        - Title name to display in ROC Curve Chart
      * - roc_description
        - ROC Curve Chart Description
        - Add Description for ROC Curve Chart
      * - xlabel
        - X Label
        - X label
      * - ylabel
        - Y Label
        - Y label


Details
===============
More details are available at : https://xgboost.readthedocs.io/en/stable/python/python_api.html#xgboost.XGBClassifier


