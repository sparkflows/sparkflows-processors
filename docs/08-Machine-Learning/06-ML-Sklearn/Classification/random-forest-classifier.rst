Sklearn Random Forest Classifier
=========== 

Random Forest Classifier, fits a number of decision tree classifiers on various sub-samples of the dataset and uses averaging to improve the predictive accuracy and control over-fitting. The sub-sample size is controlled with the max_samples parameter if bootstrap=True (default), otherwise the whole dataset is used to build each tree.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnRandomForestClassifier

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
        - NEstimators
        - Specifies the number of trees in the forest.
      * - criterion
        - Criterion
        - The function to measure the quality of a split. 'gini' for the Gini impurity and 'entropy' for the information gain.
      * - max_depth
        - MaxDepth
        - The maximum depth of the tree. If not set, nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples.
      * - min_samples_split
        - MinSamplesSplit
        - The minimum number of samples required to split an internal node. Higher values prevent creating nodes with few samples, which can be sensitive to noise.
      * - min_samples_leaf
        - MinSamplesLeaf
        - The minimum number of samples required to be at a leaf node. A split point is only considered if it leaves at least this many training samples in each of the left and right branches.
      * - min_weight_fraction_leaf
        - MinWeightFractionLeaf
        - The minimum weighted fraction of the sum total of weights required to be at a leaf node. Weights are assigned to individual samples in the construction of the tree.
      * - max_features
        - MaxFeatures
        - 
      * - max_leaf_nodes
        - MaxLeafNodes
        - Grow a tree with `max_leaf_nodes` in best-first fashion. If not set, then unlimited number of leaf nodes is used.
      * - min_impurity_decrease
        - MinImpurityDecrease
        - Generally used to control over-fitting. The higher the value, the more conservative the algorithm will be.
      * - min_impurity_split
        - MinImpuritySplit
        - 
      * - bootstrap
        - Bootstrap
        - Whether bootstrap samples are used when building trees. If False, the whole dataset is used to build each tree.
      * - oob_score
        - OobScore
        - Whether to use out-of-bag samples to estimate the generalization accuracy.
      * - random_state
        - RandomState
        - Default value is None 
      * - warm_start
        - WarmStart
        - When set to True, the existing trained trees in the model are reused and additional trees are added to the ensemble. This can save time when incrementally increasing the number of trees in the model.
      * - path
        - Save Confusion Matrix Path
        - Save Confusion Matrix
      * - confusionMatrix
        - Confusion Matrix
      * - output_confusion_matrix_chart
        - Output Confusion Matrix Chart
        - whether to display confusion matrix chart.
      * - cm_chart_title
        - Confusion Matrix Chart Title
        - Title name to display in Confusion Matrix Chart
      * - cm_chart_description
        - Confusion Matrix Chart Description
        -  Description to display in Confusion Matrix CHart
      * - confusionMatrixTargetLegend
        - Confusion Matrix Target Legend
        - Legend name to display for Target in Confusion Matrix
      * - confusionMatrixPredictedLabelLegend
        - Confusion Matrix PredictedLabel Legend
        - Legend name to display for Predicted Label in Confusion Matrix
      * - confusionMatrixCountLegend
        - Confusion Matrix Count Legend
        - Legend name to display for Count in Confusion Matrix
      * - Description
        - Confusion Matrix Description
      * - confusionMatrixRowDescription
        - Confusion Matrix Outcome description
        - One can provide the business details of the outcome of the confusion matrix rows
      * - ROC Curve
        - ROC Curve
      * - output_roc_curve
        - Output ROC Curve
        - whether to display confusion matrix chart.
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
        - Y Label


Details
-------


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html


