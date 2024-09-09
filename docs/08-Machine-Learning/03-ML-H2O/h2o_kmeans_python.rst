H2O K-Means
=========== 

K-Means falls in the general category of clustering algorithms.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OKMeans

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - maxIterations
        - Max Iterations
        - Maximum number of iterations.
      * - featuresCols
        - Feature Columns
        - Features to be used for Modelling
      * - standardize
        - Standardize
        - Standardize numeric columns to have zero mean and unit variance.
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
      * - init
        - Initialization mode
        - Initialization mode.
      * - estimateK
        - Estimate k
        - iWhether to estimate the number of clusters (<=k) iteratively and deterministically.
      * - k
        - K
        - The max. number of clusters. If estimate_k is disabled, the model will find k centroids, otherwise it will find up to k centroids.
      * - saveCentroidsPath
        - Save Centroids Path
        - Save Centroids as CSV
      * - clusterSizeConstraints
        - Cluster Size Constraint
        - An array specifying the minimum number of points that should be in each cluster. The length of the constraints array has to be the same as the number of clusters.
      * - nfolds
        - Number of Folds
        - Number of folds for K-fold cross-validation (0 to disable or >= 2).
      * - keepCrossValidationModels
        - Keep Cross Validation Models
        - Whether to keep the cross-validated models. Keeping cross-validation models may consume significantly more memory in the H2O cluster.
      * - keepCrossValidationPredictions
        - Keep Cross Validation Predictions
        - Whether to keep the predictions of the cross-validation predictions. This needs to be set to TRUE if running the same AutoML object for repeated runs because CV predictions are required to build additional Stacked Ensemble models in AutoML.
      * - keepCrossValidationFoldAssignment
        - Keep Cross Validation Fold Assignment
        - Whether to keep cross-validation assignments.
      * - foldCol
        - Fold Column
        - Column with cross-validation fold index assignment per observation.
      * - foldAssignment
        - Fold Assignment
        - Cross-validation fold assignment scheme, if fold_column is not specified. The 'Stratified' option will stratify the folds based on the response variable, for classification problems.
      * - categoricalEncoding
        - Categorical Encoding
        - Specify one of the various encoding schemes for handling categorical features
      * - ignoreConstCols
        - Ignore Const Columns
        - Ignore constant columns.
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - scoreEachIteration
        - Score Each Iteration
        - Whether to score during each iteration of model training.
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).


Details
-------


K-Means falls in the general category of clustering algorithms. Clustering is a form of unsupervised learning that tries to find structures in the data without using any labels or target values. Clustering partitions a set of observations into separate groupings such that an observation in a given group is more similar to another observation in the same group than to another observation in a different group.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/k-means.html


