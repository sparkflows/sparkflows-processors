H2O Isolation Forest
=========== 

Isolation Forest is similar in principle to Random Forest and is built on the basis of decision trees.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OIsolationForest

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - sampleSize
        - Sample Size
        - Number of randomly sampled observations used to train each Isolation Forest tree. Only one of parameters sample_size and sample_rate should be defined. If sample_rate is defined, sample_size will be ignored
      * - sampleRate
        - Sample Rate
        - Row sample rate per tree (from 0.0 to 1.0).
      * - mtries
        - mtries
        - Number of variables randomly sampled as candidates at each split. If set to -1, defaults to sqrt{p} for classification and p/3 for regression (where p is the # of predictors.
      * - contamination
        - Contamination
        - Contamination ratio - the proportion of anomalies in the input dataset. If undefined (-1) the predict function will not mark observations as anomalies and only anomaly score will be returned.
      * - ntrees
        - Number of Trees
        - Number of trees.
      * - maxDepth
        - Max Depth
        - Maximum tree depth (0 for unlimited).
      * - minRows
        - Min Rows
        - Fewest allowed (weighted) observations in a leaf.
      * - seed
        - Seed
        - Seed for pseudo random number generator (if applicable).
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
      * - categoricalEncoding
        - Categorical Encoding
        - Specify one of the various encoding schemes for handling categorical features
      * - ignoreConstCols
        - Ignore Const Columns
        - Ignore constant columns.
      * - ignoredCols
        - Ignore Columns
        - Ignore Columns.
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded
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


Details
-------


Isolation Forest is similar in principle to Random Forest and is built on the basis of decision trees. Isolation Forest, however, identifies anomalies or outliers rather than profiling normal data points. Isolation Forest isolates observations by randomly selecting a feature and then randomly selecting a split value between the maximum and minimum values of that selected feature. This split depends on how long it takes to separate the points.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/if.html


