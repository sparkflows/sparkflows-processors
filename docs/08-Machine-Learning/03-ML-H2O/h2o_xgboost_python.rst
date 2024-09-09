H2O XGBoost
=========== 

H2O XGBoost

Input
--------------
It takes in a two DataFrame as input, one is for train and other one is for validation.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OXGBoost

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
      * - path
        - Path
        - Save Confusion Matrix to Path
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
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
      * - maxBins
        - Max Bins
        - For tree_method=hist only: maximum number of bins.
      * - maxLeaves
        - Max Leaves
        - For tree_method=hist only: maximum number of leaves.
      * - treeMethod
        - Tree Method
        - Tree method.
      * - growPolicy
        - Grow Policy
        - Grow policy.
      * - booster
        - Booster
        - Booster
      * - eta
        - Eta
        - (same as learn_rate) Learning rate (from 0.0 to 1.0).
      * - sampleRate
        - Sample Rate
        - (same as subsample) Row sample rate per tree (from 0.0 to 1.0)..
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
        - Stopping Metric
        - Metric to use for early stopping (AUTO: logloss for classification, deviance for regression)
      * - stoppingTolerance
        - Stopping Tolerance
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
      * - minChildWeight
        - Min Child Weight
        - (same as min_rows) Fewest allowed (weighted) observations in a leaf.
      * - learnRate
        - Learn Rate
        - (Same as eta) Learning rate (from 0.0 to 1.0).
      * - subsample
        - Sample Rate
        - (same as sample_rate) Row sample rate per tree (from 0.0 to 1.0).
      * - colSampleRate
        - Column Sample Rate
        - Column sample rate(from 0.0 to 1.0).
      * - colSampleByLevel
        - Column Sample By Level
        - (same as col_sample_rate) Column sample rate (from 0.0 to 1.0).
      * - colSampleRatePerTree
        - Column Sample Rate Per Tree
        - (same as colsample_bytree) Column sample rate per tree (from 0.0 to 1.0).
      * - colSampleByTree
        - Column Sample By Tree
        - (same as col_sample_rate_per_tree) Column sample rate per tree (from 0.0 to 1.0).
      * - colSampleByNode
        - Column Sample By Node
        - Column sample rate per tree node (from 0.0 to 1.0).
      * - maxAbsLeafnodePred
        - Max Absolute Leaf Node Prediction
        - (same as max_delta_step) Maximum absolute value of a leaf node prediction.
      * - maxDeltaStep
        - Max Delta Step
        - (same as max_abs_leafnode_pred) Maximum absolute value of a leaf node prediction.
      * - scoreTreeInterval
        - Score Tree Interval
        - Score the model after every so many trees. Disabled if set to 0.
      * - minSplitImprovement
        - Minimum Split Improvement
      * - gamma
        - Gamma
      * - nthreads
        - Number of Trees
        - Number of parallel threads that can be used to run XGBoost. Cannot exceed H2O cluster limits (-nthreads parameter). Defaults to maximum available.
      * - buildTreeOneNode
        - Build tree one node
        - Enables to run on a single node
      * - calibrateModel
        - Calibrate Model
        - Use Platt Scaling to calculate calibrated class probabilities. Calibration can provide more accurate estimates of class probabilities.
      * - regLambda
        - Reg Lambda
        - L2 regularization.
      * - regAlpha
        - Reg Alpha
        - L1 regularization.
      * - quietMode
        - Quiet mode
        - Enable quiet mode for less output to standard output.
      * - sampleType
        - Sample Type
        - For booster=dart only: sample_type
      * - normalizeType
        - Normalize Type
        - For booster=dart only: normalize_type
      * - rateDrop
        - Rate Drop
        - For booster=dart only: rate_drop (0..1).
      * - oneDrop
        - One Drop
        - For booster=dart only: one_drop.
      * - skipDrop
        - Skip Drop
        - For booster=dart only: skip_drop (0..1).
      * - dmatrixType
        - Dmatrix Type
        - Type of DMatrix. For sparse, NAs and 0 are treated equally.
      * - scalePosWeight
        - Scaled Pos Weight
        - Controls the effect of observations with positive labels in relation to the observations with negative labels on gradient calculation. Useful for imbalanced problems.
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
        - Distribution function.)
      * - tweediePower
        - Tweedie Power
        - Tweedie power for Tweedie regression, must be between 1 and 2.
      * - quantileAlpha
        - Quantile Alhpa
        - Desired quantile for Quantile regression, must be between 0 and 1.
      * - huberAlpha
        - Huber Alpha
        - Desired quantile for Huber/M-regression (threshold between quadratic and linear loss, must be between 0 and 1).
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




