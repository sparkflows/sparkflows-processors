H2O Generalized Low Rank Models
=========== 

Generalized Low Rank Models (GLRM) is an algorithm for dimensionality reduction of a dataset

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OGLRM

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Input Columns.
      * - transform
        - Transform
        - STransformation of training data
      * - k
        - K
        - Rank of matrix approximation.
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
      * - loss
        - Loss
        - Numeric loss function
      * - multiLoss
        - Multi Loss
        - Categorical loss function
      * - period
        - Period
        - SLength of period (only used with periodic loss function). 
      * - regularizationX
        - Regularization X
        - Regularization function for X matrix
      * - regularizationY
        - Regularization Y
        - Regularization function for X matrix
      * - gammaX
        - Gamma X
        - Regularization weight on X matrix
      * - gammaY
        - Gamma Y
        - Regularization weight on Y matrix.
      * - maxIterations
        - Max Iterations
        - Maximum number of iterations.
      * - maxUpdates
        - Max Updates
        - Maximum number of Updated.
      * - initStepSize
        - Init Step Size
        - Initial step size.
      * - minStepSize
        - Min Step Size
        - Minimum step size.
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
      * - init
        - Init
        - STransformation of training data
      * - svdMethod
        - SVD Method
        - STransformation of training data
      * - loadingName
        - Loading Name
        - [Deprecated] Use representation_name instead.  Frame key to save resulting X.
      * - representationName
        - Representation Name
        - SFrame key to save resulting X.
      * - expandUserY
        - Expand User Y
        - Expand categorical columns in user-specified initial Y.
      * - imputeOriginal
        - Impute Original
        - Reconstruct original training data by reversing transform.
      * - recoverSvd
        - Recover SVD
        - Recover singular values and eigenvectors of XY.
      * - ignoreConstCols
        - Ignore Constant Columns
        - Ignore constant columns.
      * - scoreEachIteration
        - Score Each Iteration
        - Whether to score during each iteration of model training.
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).
      * - reconstructedCol
        - Reconstructed Column
        - Reconstructed Column Name
      * - maxScoringIterations
        - Max Scoring Iterations
        - Max Scoring Iterations.


Details
-------


Generalized Low Rank Models (GLRM) is an algorithm for dimensionality reduction of a dataset. It is a general, parallelized optimization algorithm that applies to a variety of loss and regularization functions. Categorical columns are handled by expansion into 0/1 indicator columns for each level. With this approach, GLRM is useful for reconstructing missing values and identifying important features in heterogeneous data.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/glrm.html


