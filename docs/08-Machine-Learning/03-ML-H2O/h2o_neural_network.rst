H2O Neural Network
=========== 

H2O Deep Learning is based on a multi-layer feedforward artificial neural network that is trained with stochastic gradient descent using back-propagation.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2ONeuralNetwork

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - isResponseIsCategorical
        - isResponseColIsCategorical
        - Specify a response column type(numeric or categorical). Separates the Classification and Regression
      * - labelCol
        - Label Column
        - Response variable column.
      * - ignoredCols
        - Ignored Columns
        - Features to be ignored for Modelling
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
      * - balanceClasses
        - Balance Classes
        - Balance training data class counts via over/under-sampling (for imbalanced data).
      * - maxAfterBalanceSize
        - Max After Balance Size
        - Maximum relative size of the training data after balancing class counts (can be less than 1.0). Requires balance_classes.
      * - activation
        - Activation
        - Activation function.
      * - hidden
        - Hidden
        - Specify the hidden layer sizes (value must be positive)
      * - epochs
        - Epochs
        - SHow many times the dataset should be iterated (streamed), can be fractional.
      * - nfolds
        - Number of Folds
        - Number of folds for K-fold cross-validation (0 to disable or >= 2).
      * - trainSamplesPerIteration
        - Train Samples Per Iteration
        - Number of training samples (globally) per MapReduce iteration. Special values are 0: one epoch, -1: all available data (e.g., replicated training data), -2: automatic.
      * - targetRatioCommToComp
        - Target ratio comm to comp
        - Target ratio of communication overhead to computation. Only for multi-node operation and train_samples_per_iteration = -2 (auto-tuning).
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
      * - standardize
        - Standardize
        - If enabled, automatically standardize the data. If disabled, the user must provide properly scaled input data.
      * - loss
        - Loss
        - SLoss function.
      * - adaptiveRate
        - Adaptive Rate
        - Adaptive learning rate.
      * - rho
        - Rho
        - Adaptive learning rate time decay factor (similarity to prior updates).
      * - advanced
        - Advanced
      * - epsilon
        - Epsilon
        - Adaptive learning rate smoothing factor (to avoid divisions by zero and allow progress).
      * - rate
        - Rate
        - Learning rate (higher => less stable, lower => slower convergence).
      * - rateAnnealing
        - Rate Annealing
        - Learning rate annealing: rate / (1 + rate_annealing * samples).
      * - rateDecay
        - Rate Decay
        - Learning rate decay factor between layers (N-th layer: rate * rate_decay ^ (n - 1)
      * - momentumStart
        - Momentum Start
        - Specify the initial momentum at the beginning of training; we suggest 0.5 (Applicable only if adaptive_rate is disabled)
      * - momentumRamp
        - Momentum Ramp
        - Number of training samples for which momentum increases.
      * - momentumStable
        - Momentum Stable
        - Final momentum after the ramp is over (try 0.99).
      * - nesterovAcceleratedGradient
        - Nesterov Accelerated Gradient
        - Use Nesterov accelerated gradient (recommended).
      * - inputDropoutRatio
        - Input Dropout Ratio
        - Input layer dropout ratio (can improve generalization, try 0.1 or 0.2).
      * - inputDropoutRatio
        - Hidden Dropout Ratios
        - Hidden layer dropout ratios (can improve generalization), specify one value per hidden layer, defaults to 0.5.
      * - l1
        - L1
        - L1 regularization (can add stability and improve generalization, causes many weights to become 0).
      * - l2
        - L2
        - L2 regularization (can add stability and improve generalization, causes many weights to be small.
      * - maxW2
        - Max W2
        - Constraint for squared sum of incoming weights per unit (e.g. for Rectifier).
      * - initialWeightDistribution
        - Initial Weight Distribution
        - Initial weight distribution.
      * - initialWeightScale
        - Initial Weight Scale
        - Uniform: -value...value, Normal: stddev.
      * - scoreInterval
        - Score interval
        - Shortest time interval (in seconds) between model scoring.
      * - scoreTrainingSamples
        - Score Training Samples
        - Number of training set samples for scoring (0 for all).
      * - scoreValidationSamples
        - Score Validation Samples
        - Number of validation set samples for scoring (0 for all).
      * - scoreDutyCycle
        - Score Duty Cycle
        - Maximum duty cycle fraction for scoring (lower: more training, higher: more scoring).
      * - classificationStop
        - Classification Stop
        - Stopping criterion for classification error fraction on training data (-1 to disable).
      * - regressionStop
        - Regression Stop
        - Stopping criterion for regression error (MSE) on training data (-1 to disable).
      * - quietMode
        - Quiet mode
        - Enable quiet mode for less output to standard output.
      * - scoreValidationSampling
        - Score Validation Sampling
        - Method used to sample validation dataset for scoring.
      * - overwriteWithBestModel
        - Overwrite With Best Model
        - If enabled, override the final model with the best model found during training.
      * - useAllFactorLevels
        - Use All Factor Levels
        - Use all factor levels of categorical variables. Otherwise, the first factor level is omitted (without loss of accuracy). Useful for variable importances and auto-enabled for autoencoder.
      * - diagnostics
        - Diagnostics
        - Enable diagnostics for hidden layers.
      * - calculateFeatureImportances
        - Calculate Feature Importances
        - Compute variable importances for input features (Gedeon method) - can be slow for large networks.
      * - fastMode
        - Fast Mode
        - SEnable fast mode (minor approximation in back-propagation).
      * - forceLoadBalance
        - Force Load Balance
        - Force extra load balancing to increase training speed for small datasets (to keep all cores busy).
      * - replicateTrainingData
        - Replicate Training Data
        - Replicate the entire training dataset onto every node for faster training on small datasets.
      * - singleNodeMode
        - Single Node Mode
        - Run on a single node for fine-tuning of model parameters.
      * - shuffleTrainingData
        - Shuffle Training Data
        - Enable shuffling of training data (recommended if training data is replicated and train_samples_per_iteration is close to #nodes x #rows, of if using balance_classes).
      * - missingValuesHandling
        - Missing Values Handling
        - Handling of missing values. Either MeanImputation or Skip.
      * - sparse
        - Sparse
        - Sparse data handling (more efficient for data with lots of 0 values).
      * - averageActivation
        - Average Activation
        - Average activation for sparse auto-encoder. #Experimental.
      * - sparsityBeta
        - Sparsity Beta
        - Sparsity regularization. #Experimental.
      * - maxCategoricalFeatures
        - Max Categorical Features
        - Max. number of categorical features, enforced via hashing. #Experimental.
      * - reproducible
        - Reproducible
        - Force reproducibility on small data (will be slow - only uses 1 thread).
      * - exportWeightsAndBiases
        - Export Weights And Biases
        - Whether to export Neural Network weights and biases to H2O Frames.
      * - miniBatchSize
        - Mini Batch Size
        - SMini-batch size (smaller leads to better fit, larger can speed up and generalize better).
      * - elasticAveraging
        - Elastic Averaging
        - Elastic averaging between compute nodes can improve distributed model convergence. #Experimental.
      * - elasticAveragingMovingRate
        - Elastic Averaging Moving Rate
        - Elastic averaging moving rate (only if elastic averaging is enabled).
      * - elasticAveragingRegularization
        - Elastic Averaging Regularization
        - Elastic averaging regularization strength (only if elastic averaging is enabled).
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


Details
-------


H2O’s Deep Learning is based on a multi-layer feedforward artificial neural network that is trained with stochastic gradient descent using back-propagation. The network can contain a large number of hidden layers consisting of neurons with tanh, rectifier, and maxout activation functions.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/deep-learning.html


