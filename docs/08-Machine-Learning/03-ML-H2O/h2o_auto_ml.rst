H2O Auto ML
=========== 

H2O AutoML

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OAutoML

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
      * - cmpath
        - Path
        - Save Confusion Matrix to Path
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - path
        - Path
        - Model Save Path.
      * - seed
        - Seed
        - Seed for random number generator; set to a value other than -1 for reproducibility.
      * - balanceClasses
        - Balance Classes
        - Balance training data class counts via over/under-sampling (for imbalanced data).
      * - nfolds
        - N Folds
        - Number of folds for k-fold cross-validation (defaults to -1 (AUTO), otherwise it must be >=2 or use 0 to disable).
      * - maxModels
        - Max Models
        - Maximum number of models to build (optional). Always set this parameter to ensure AutoML reproducibility: all models are then trained until convergence and none is constrained by a time budget.
      * - includeAlgos
        - Include Algos
        - A list of algorithms to restrict to during the model-building phase.Default all Algos is included
      * - excludeAlgos
        - Exclude Algos
        - A list of algorithms to skip during the model-building phase.
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).
      * - stoppingRounds
        - Stopping Rounds
        - Early stopping based on convergence of stopping_metric. Stop if simple moving average of length k of the stopping_metric does not improve for k:=stopping_rounds scoring events (0 to disable).
      * - stoppingMetric
        - Stopping Metric
        - Metric to use for early stopping (AUTO: logloss for classification, deviance for regression)
      * - stoppingTolerance
        - Stopping Tolerance
        - Relative tolerance for metric-based stopping criterion (stop if relative improvement is not at least this much)
      * - withContributions
        - With Contributions
        - Enables or disables generating a sub-column of detailedPredictionCol containing Shapley values.
      * - advanced
        - Advanced
      * - convertUnknownCategoricalLevelsToNa
        - Convert Unknown Categorical Levels to NA
        - If set to ‘true’, the model converts unknown categorical levels to NA during making predictions.
      * - sortMetric
        - Sort Metric
        - Metric to sort the leaderboard by. Defaults to AUTO
      * - maxRuntimeSecsPerModel
        - Max Runtime in Seconds per Model
        - Maximum time to spend on each individual model (optional). Note that models constrained by a time budget are not guaranteed reproducible.
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
      * - maxAfterBalanceSize
        - Max After Balance Size
        - Maximum relative size of the training data after balancing class counts (defaults to 5.0 and can be less than 1.0). Requires balance_classes.
      * - keepCrossValidationPredictions
        - Keep Cross Validation Predictions
        - Whether to keep the predictions of the cross-validation predictions. This needs to be set to TRUE if running the same AutoML object for repeated runs because CV predictions are required to build additional Stacked Ensemble models in AutoML.
      * - keepCrossValidationModels
        - Keep Cross Validation Models
        - Whether to keep the cross-validated models. Keeping cross-validation models may consume significantly more memory in the H2O cluster.
      * - keepCrossValidationFoldAssignment
        - Keep Cross Validation Fold Assignment
        - Whether to keep cross-validation assignments.
      * - distribution
        - Distribution
        - Distribution function used by algorithms that support it; other algorithms use their defaults.
      * - tweediePower
        - Tweedie Power
        - Tweedie power for Tweedie regression, must be between 1 and 2.
      * - quantileAlpha
        - Quantile Alpha
        - Desired quantile for Quantile regression, must be between 0 and 1.
      * - huberAlpha
        - Huber Alpha
        - Desired quantile for Huber/M-regression (threshold between quadratic and linear loss, must be between 0 and 1).
      * - exploitationRatio
        - Exploitation Ratio
        - The budget ratio (between 0 and 1) dedicated to the exploitation (vs exploration) phase.
      * - foldCol
        - Fold Column
        - Column with cross-validation fold index assignment per observation.
      * - weightCol
        - Weight Column
        - Column with observation weights. Giving some observation a weight of zero is equivalent to excluding it from the dataset; giving an observation a relative weight of 2 is equivalent to repeating that row twice. Negative weights are not allowed. Note: Weights are per-row observation weights and do not increase the size of the data frame. This is typically the number of times a row is repeated, but non-integer values are supported as well. During training, rows with higher weights matter more, due to the larger loss function pre-factor. If you set weight = 0 for a row, the returned prediction frame at that row is zero and this is incorrect. To get an accurate prediction, remove all rows with weight == 0.


Details
-------


H2O AutoML(for Regression and Classification) The H2O AutoML interface is designed to have as few parameters as possible so that all the user needs to do is point to their dataset, identify the response column and optionally specify a time constraint or limit on the number of total models trained.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/automl.html#automl-automatic-machine-learning


