H2O Distributed Random Forest
=========== 

Distributed Random Forest (DRF) is a powerful classification and regression tool. DRF generates a forest of classification or regression trees.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2ODRF

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - isResponseIsCategorical
        - Is Response Column Categorical
        - Specify a response column type(numeric or categorical). Separates the Classification and Regression
      * - labelCol
        - Label Column
        - Response variable column.
      * - featuresCols
        - Feature Columns
        - Features to be used for Modelling
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - path
        - Path
        - Save Confusion Matrix to Path
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
      * - balanceClasses
        - Balance Classes
        - Balance training data class counts via over/under-sampling (for imbalanced data).
      * - splitRatio
        - Split Ratio
        - Split Ratio
      * - nfolds
        - Number of Folds
        - Number of folds for K-fold cross-validation (0 to disable or >= 2).
      * - ntrees
        - Number of Trees
        - Number of trees.
      * - maxDepth
        - Max Depth
        - Maximum tree depth (0 for unlimited).
      * - minRows
        - Min Rows
        - Fewest allowed (weighted) observations in a leaf.
      * - nbins
        - Number of Bins
        - For numerical columns (real/int), build a histogram of (at least) this many bins, then split at the best point.
      * - nbinsTopLevel
        - Number of bins top level
        - For numerical columns (real/int), build a histogram of (at most) this many bins at the root level, then decrease by factor of two per level.
      * - nbinsCats
        - Number of Bins Categoricals
        - For categorical columns (factors), build a histogram of this many bins, then split at the best point. Higher values can lead to more overfitting.
      * - categoricalEncoding
        - Categorical Encoding
        - Specify one of the various encoding schemes for handling categorical features
      * - ignoreConstCols
        - Ignore Const Columns
        - Ignore constant columns.
      * - scoreEachIteration
        - Score Each Iteration
        - Whether to score during each iteration of model training.
      * - stoppingRounds
        - Stopping Rounds
        - Early stopping based on convergence of stopping_metric. Stop if simple moving average of length k of the stopping_metric does not improve for k:=stopping_rounds scoring events (0 to disable).
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).
      * - stoppingMetric
        - StoppingMetric
        - Metric to use for early stopping (AUTO: logloss for classification, deviance for regression)
      * - stoppingTolerance
        - StoppingTolerance
        - Relative tolerance for metric-based stopping criterion (stop if relative improvement is not at least this much)
      * - gainsliftBins
        - Gains Lift Bins
        - Gains/Lift table number of bins. 0 means disabled.. Default value -1 means automatic binning.
      * - withContributions
        - With Contributions
        - Enables or disables generating a sub-column of detailedPredictionCol containing Shapley values.
      * - advanced
        - Advanced
      * - convertUnknownCategoricalLevelsToNa
        - Convert Unknown Categorical Levels to NA
        - If set to ‘true’, the model converts unknown categorical levels to NA during making predictions.
      * - predictionCol
        - Prediction Column
        - Prediction column name
      * - detailedPredictionCol
        - Detailed Prediction column
        - Column containing additional prediction details, its content depends on the model type
      * - withLeafNodeAssignments
        - With Node Assignments
        - Enables or disables computation of leaf node assignments.
      * - withStageResults
        - With Stage Results
        - Enables or disables computation of stage results.
      * - mtries
        - mtries
        - Number of variables randomly sampled as candidates at each split. If set to -1, defaults to sqrt{p} for classification and p/3 for regression (where p is the # of predictors.
      * - binomialDoubleTrees
        - Binomial Double trees
        - For binary classification: Build 2x as many trees (one per class) - can lead to higher accuracy.
      * - sampleRate
        - Sample Rate
        - Row sample rate per tree (from 0.0 to 1.0).
      * - maxAfterBalanceSize
        - Max After Balance Size
        - Maximum relative size of the training data after balancing class counts (can be less than 1.0). Requires balance_classes.
      * - maxConfusionMatrixSize
        - Max Confusion Matrix Size
        - [Deprecated] Maximum size (# classes) for confusion matrices to be printed in the Logs.
      * - buildTreeOneNode
        - Build tree one node
        - Enables to run on a single node
      * - colSampleRatePerTree
        - Column Sample Rate Per Tree (from 0.0 to 1.0).
        - Column sample rate per tree (from 0.0 to 1.0).
      * - colSampleRateChangePerLevel
        - Column Sample Rate change Per Level
        - Relative change of the column sampling rate for every level (must be > 0.0 and <= 2.0).
      * - scoreTreeInterval
        - Score Tree Interval
        - Score the model after every so many trees. Disabled if set to 0.
      * - minSplitImprovement
        - Minimum Split Improvement
      * - histogramType
        - Histogram Type
        - What type of histogram to use for finding optimal split points. Possible values are 
      * - calibrateModel
        - Calibrate Model
        - Use Platt Scaling to calculate calibrated class probabilities. Calibration can provide more accurate estimates of class probabilities.
      * - checkConstantResponse
        - Check Constant Response
        - UCheck if response column is constant. If enabled, then an exception is thrown if the response column is a constant value.If disabled, then model will train regardless of the response column being a constant value or not.
      * - keepCrossValidationModels
        - Keep Cross Validation Models
        - Whether to keep the cross-validated models. Keeping cross-validation models may consume significantly more memory in the H2O cluster.
      * - keepCrossValidationPredictions
        - Keep Cross Validation Predictions
        - Whether to keep the predictions of the cross-validation predictions. This needs to be set to TRUE if running the same AutoML object for repeated runs because CV predictions are required to build additional Stacked Ensemble models in AutoML.
      * - keepCrossValidationFoldAssignment
        - Keep Cross Validation Fold Assignment
        - Whether to keep cross-validation assignments.
      * - distribution
        - Distribution
        - Distribution function used by algorithms that support it; other algorithms use their defaults.
      * - weightCol
        - Weight Column
        - Column with observation weights. Giving some observation a weight of zero is equivalent to excluding it from the dataset; giving an observation a relative weight of 2 is equivalent to repeating that row twice. Negative weights are not allowed. Note: Weights are per-row observation weights and do not increase the size of the data frame. This is typically the number of times a row is repeated, but non-integer values are supported as well. During training, rows with higher weights matter more, due to the larger loss function pre-factor. If you set weight = 0 for a row, the returned prediction frame at that row is zero and this is incorrect. To get an accurate prediction, remove all rows with weight == 0.
      * - offsetCol
        - Offset Column
        - Offset column. This will be added to the combination of columns before applying the link function.
      * - foldCol
        - Fold Column
        - Column with cross-validation fold index assignment per observation.
      * - foldAssignment
        - Fold Assignment
        - Cross-validation fold assignment scheme, if fold_column is not specified. The 'Stratified' option will stratify the folds based on the response variable, for classification problems.
      * - aucType
        - AUC Type
        - Set default multinomial AUC type.
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




