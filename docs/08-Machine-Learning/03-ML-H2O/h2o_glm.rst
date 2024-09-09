H2O Generalized Linear Models
=========== 

Generalized Linear Models (GLM) estimate regression models for outcomes following exponential distributions

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OGlm

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
      * - balanceClasses
        - Balance Classes
        - Balance training data class counts via over/under-sampling (for imbalanced data).
      * - nfolds
        - Number of Folds
        - Number of folds for K-fold cross-validation (0 to disable or >= 2).
      * - maxIterations
        - Max Iterations
        - Maximum number of iterations.
      * - theta
        - Theta
        - Theta
      * - solver
        - Solver
        - Specify the solver to use (AUTO, IRLSM, L_BFGS, COORDINATE_DESCENT_NAIVE, COORDINATE_DESCENT, GRADIENT_DESCENT_LH, or GRADIENT_DESCENT_SQERR)
      * - earlyStopping
        - Early Stopping
        - Stop early when there is no more relative improvement on train or validation (if provided).
      * - removeCollinearCols
        - Remove Collinear Columns
        - In case of linearly dependent columns, remove some of the dependent columns.
      * - family
        - Family
        - Family. Use binomial for classification with logistic regression, others are for regression problems. 
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
      * - standardize
        - Standardize
        - Standardize numeric columns to have zero mean and unit variance.
      * - intercept
        - Intercept
        - Include constant term in the model.
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
      * - tweedieVariancePower
        - Tweedie Variance Power
        - tweedieVariancePower
      * - tweedieLinkPower
        - Tweedie Link Power
        - Tweedie link power.
      * - lambdaSearch
        - Lambda Search
        - Use lambda search starting at lambda max, given lambda is then interpreted as lambda min.
      * - nlambdas
        - Number of Lambdas
        - Number of lambdas to be used in a search. Default indicates: If alpha is zero, with lambda search set to True, the value of nlamdas is set to 30 (fewer lambdas are needed for ridge regression) otherwise it is set to 100.
      * - scoreIterationInterval
        - Score Iteration Interval
        - Score Iteration Interval
      * - coldStart
        - Cold Start
        - Only applicable to multiple alpha/lambda values.  If false, build the next model for next set of alpha/lambda values starting from the values provided by current model.  If true will start GLM model from scratch.
      * - missingValuesHandling
        - Missing Values Handling
        - Handling of missing values.
      * - nonNegative
        - Non Negative
        - Restrict coefficients (not intercept) to be non-negative.
      * - betaEpsilon
        - Beta Epsilon
        - Converge if  beta changes less (using L-infinity norm) than beta esilon, ONLY applies to IRLSM solver .
      * - objectiveEpsilon
        - Objective Epsilon
        - SConverge if  objective value changes less than this. Default (of -1.0) indicates: If lambda_search is set to True the value of objective_epsilon is set to .0001. If the lambda_search is set to False and lambda is equal to zero, the value of objective_epsilon is set to .000001, for any other value of lambda the default value of objective_epsilon is set to .0001.
      * - gradientEpsilon
        - Gradient Epsilon
        - SConverge if  objective changes less (using L-infinity norm) than this, ONLY applies to L-BFGS solver. Default (of -1.0) indicates: If lambda_search is set to False and lambda is equal to zero, the default value of gradient_epsilon is equal to .000001, otherwise the default value is .0001. If lambda_search is set to True, the conditional values above are 1E-8 and 1E-6 respectively.
      * - objReg
        - Objective Regularizer
        - Likelihood divider in objective value computation, default (of -1.0) will set it to 1/nobs.
      * - link
        - Link
        - Link function
      * - calcLike
        - Calc Like
        - if true, will return likelihood function value for HGLM.
      * - HGLM
        - HGLM
        - If set to true, will return HGLM model.  Otherwise, normal GLM model will be returned.
      * - prior
        - Prior
        - SPrior probability for y==1. To be used only for logistic regression iff the data has been sampled and the mean of response does not reflect reality.
      * - lambdaMinRatio
        - Lambda Min Ratio
        - Minimum lambda used in lambda search, specified as a ratio of lambda_max (the smallest lambda that drives all coefficients to zero). Default indicates: if the number of observations is greater than the number of variables, then lambda_min_ratio is set to 0.0001; if the number of observations is less than the number of variables, then lambda_min_ratio is set to 0.01.
      * - maxActivePredictors
        - Max Active Predictors
        - SMaximum number of active predictors during computation. Use as a stopping criterion to prevent expensive model building with many predictors. Default indicates: If the IRLSM solver is used, the value of max_active_predictors is set to 5000 otherwise it is set to 100000000.
      * - maxAfterBalanceSize
        - Max After Balance Size
        - Maximum relative size of the training data after balancing class counts (can be less than 1.0). Requires balance_classes.
      * - maxConfusionMatrixSize
        - Max Confusion Matrix Size
        - [Deprecated] Maximum size (# classes) for confusion matrices to be printed in the Logs.
      * - computePValues
        - Compute P Values
        - Request p-values computation, p-values work only with IRLSM solver and no regularization.
      * - generateScoringHistory
        - Generate Scoring History
        - If set to true, will generate scoring history for GLM.  This may significantly slow down the algo.
      * - keepCrossValidationModels
        - Keep Cross Validation Models
        - Whether to keep the cross-validated models. Keeping cross-validation models may consume significantly more memory in the H2O cluster.
      * - keepCrossValidationPredictions
        - Keep Cross Validation Predictions
        - Whether to keep the predictions of the cross-validation predictions. This needs to be set to TRUE if running the same AutoML object for repeated runs because CV predictions are required to build additional Stacked Ensemble models in AutoML.
      * - keepCrossValidationFoldAssignment
        - Keep Cross Validation Fold Assignment
        - Whether to keep cross-validation assignments.
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
      * - ROC Curve
        - ROC Curve
      * - output_roc_curve
        - Output ROC Curve
        - Whether to display confusion matrix chart.
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


Generalized Linear Models (GLM) estimate regression models for outcomes following exponential distributions. In addition to the Gaussian (i.e. normal) distribution, these include Poisson, binomial, and gamma distributions. Each serves a different purpose, and depending on distribution and link function choice, can be used either for prediction or classification.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/glm.html


