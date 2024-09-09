H2O PCA
=========== 

PCA is commonly used to model without regularization or perform dimensionality reduction. It can also be useful to carry out as a preprocessing step before distance-based algorithms such as K-Means since PCA guarantees that all dimensions of a manifold are orthogonal.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OPCA

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - transform
        - Transform
        - Transformation of training data.
      * - pcaMethod
        - PCA Method
        - Specify the algorithm to use for computing the principal components: GramSVD - uses a distributed computation of the Gram matrix, followed by a local SVD; Power - computes the SVD using the power iteration method (experimental); Randomized - uses randomized subspace iteration method; GLRM - fits a generalized low-rank model with L2 loss function and no regularization and solves for the SVD using local matrix algebra (experimental).
      * - pcaImpl
        - PCA Implementation
        - Specify the implementation to use for computing PCA (via SVD or EVD): MTJ_EVD_DENSEMATRIX - eigenvalue decompositions for dense matrix using MTJ; MTJ_EVD_SYMMMATRIX - eigenvalue decompositions for symmetric matrix using MTJ; MTJ_SVD_DENSEMATRIX - singular-value decompositions for dense matrix using MTJ; JAMA - eigenvalue decompositions for dense matrix using JAMA. References: JAMA - http://math.nist.gov/javanumerics/jama/; MTJ - https://github.com/fommil/matrix-toolkits-java/.
      * - k
        - K
        - Rank of matrix approximation.
      * - maxIterations
        - Max Iterations
        - Maximum training iterations.
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
      * - useAllFactorLevels
        - Use All Factor Levels
        - Whether first factor level is included in each categorical expansion.
      * - computeMetrics
        - Compute Metrics
        - Whether to compute metrics on the training data.
      * - imputeMissing
        - Impute Missing
        - Whether to impute missing entries with the column mean.
      * - ignoreConstCols
        - Ignore Const Columns
        - Ignore constant columns.
      * - scoreEachIteration
        - Score Each Iteration
        - Whether to score during each iteration of model training.
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).
      * - ignoredCols
        - Ignored Columns
        - Features to be ignored for Modelling
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded


Details
-------


Principal Components Analysis (PCA) is closely related to Principal Components Regression. The algorithm is carried out on a set of possibly collinear features and performs a transformation to produce a new set of uncorrelated features.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/pca.html


