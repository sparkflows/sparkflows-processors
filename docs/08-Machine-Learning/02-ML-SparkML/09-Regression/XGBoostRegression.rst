XGBoost Regressor
=========== 



Input
--------------
It takes in a DataFrame as input and performs XGBoost Regression

Output
--------------
The XGBoost Model generated is passed along to the next nodes. The input DataFrame is also passed along to the next nodes

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeXGBoostRegressor

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - featuresCol
        - Features Column
        - Features column of type vectorUDT for model fitting
      * - labelCol
        - Label Column
        - The label column for model fitting
      * - predictionCol
        - Prediction Column
        - The prediction column created during model scoring.
      * - maxDepth
        - Max Depth
        - The Maximum depth of a tree
      * - maxBins
        - Max Bins
        - The maximum number of bins used for discretizing continuous features.Must be >= 2 and >= number of categories in any categorical feature.
      * - maxLeaves
        - Max Leaves
        - 
      * - numRound
        - Num Round
        - 
      * - numWorkers
        - Num Workers
        - 
      * - objective
        - Objective
        - 
      * - eta
        - Eta
        - 
      * - regLambda
        - Reg Lambda
        - 
      * - regAlpha
        - Reg Alpha
        - 
      * - subsample
        - Sub Aample
        - 
      * - sampleType
        - Sample Type
        - 
      * - treeMethod
        - Tree Method
        - 
      * - useExternalMemory
        - Use External Memory
        - 
      * - seed
        - Seed
        - 
      * - baseScore
        - Base Score
        - 
      * - minChildWeight
        - Min Child Weight
        - 
      * - colsampleBylevel
        - Col Sample By Level
        - 
      * - colsampleBytree
        - Col Sample By Tree
        - 
      * - minSplitLoss
        - Min Split Loss
        - 
      * - maxDeltaStep
        - Max Delta Step
        - 
      * - sketchEps
        - Sketch Eps
        - 
      * - scalePosWeight
        - Scale Pos Weight
        - 
      * - growPlicy
        - Grow Policy
        - 
      * - normalizeType
        - Normalize Type
        - 
      * - skipDrop
        - Skip Drop
        - 
      * - rateDrop
        - Rate Drop
        - 


Details
-------


Deatils: https://xgboost.readthedocs.io/en/latest/jvm/xgboost4j_spark_tutorial.html#xgboost4j-spark-tutorial-version-0-9


