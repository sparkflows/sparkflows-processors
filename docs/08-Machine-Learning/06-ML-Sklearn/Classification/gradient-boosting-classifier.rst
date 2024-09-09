Sklearn Gradient Boosting Classifier
=========== 

Gradient Boosting Classifier, builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary differentiable loss functions. In each stage n_classes_ regression trees are fit on the negative gradient of the binomial or multinomial deviance loss function. Binary classification is a special case where only a single regression tree is induced.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnGradientBoostingClassifier

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
        - The loss function to be optimized. 'Deviance' refers to deviance (= logistic regression) for classification with probabilistic outputs.
      * - learning_rate
        - LearningRate
        - Learning rate shrinks the contribution of each tree by learning_rate.
      * - n_estimators
        - NEstimators
        - The number of boosting stages to be run.
      * - subsample
        - Subsample
        - The fraction of samples to be used for fitting the individual base learners.
      * - criterion
        - Criterion
        - The function to measure the quality of a split.
      * - min_samples_split
        - MinSamplesSplit
        - The minimum number of samples required to split an internal node.
      * - min_samples_leaf
        - MinSamplesLeaf
        - The minimum number of samples required to be at a leaf node.
      * - min_weight_fraction_leaf
        - MinWeightFractionLeaf
        - The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node.
      * - max_depth
        - MaxDepth
        - Maximum depth of the individual regression estimators.
      * - min_impurity_decrease
        - MinImpurityDecrease
        - A node will be split if this split induces a decrease of the impurity greater than or equal to this value.
      * - min_impurity_split
        - MinImpuritySplit
        - Threshold for early stopping in tree growth. A node will split if its impurity is above the threshold.
      * - random_state
        - RandomState
        - Controls the randomness of the bootstrapping of the samples used when building trees.
      * - verbose
        - Verbose
        - Enable verbose output. If 1 then it prints progress and performance once in a while (the more trees the lower the frequency).
      * - max_leaf_nodes
        - MaxLeafNodes
        - Default value is None i.e -1
      * - warm_start
        - WarmStart
        - 
      * - presort
        - Presort
        - 
      * - validation_fraction
        - ValidationFraction
        - 
      * - n_iter_no_change
        - NIterNoChange
        - Default value is None i.e -1
      * - tol
        - Tol
        - 
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


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html


