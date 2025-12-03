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
      * - splitRatio
        - Split Ratio
        - Split Ratio
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


XGBoost Regressor Node Details
+++++++++++++++


This node implements the XGBoost algorithm for regression tasks. It can be used for a variety of regression problems, including predicting continuous values, such as stock prices, house prices, or weather patterns.


Key Parameters:


Features Column: The name of the column containing the features used for training.

Label Column: The name of the column containing the target variable to be predicted.

Prediction Column: The name of the column where the predicted values will be stored.

Max Depth: The maximum depth of each tree in the ensemble. Higher values can lead to overfitting.

Max Bins: The maximum number of bins to use for histogram-based approximations.

Max Leaves: The maximum number of leaves per tree.

Num Round: The number of boosting rounds (trees) to build.

Num Workers: The number of threads to use for parallel processing.

Objective: The objective function to optimize. 'reg:linear' is used for linear regression.

Eta: The learning rate, which controls the step size at each boosting round.

se.


Examples
-------
XGBoost Regressor Node Example
+++++++++++++++


Scenario:


Let's assume we have a dataset containing information about houses, including features like size, number of bedrooms, location, etc., and the corresponding target variable being the house price. 


Configuration:


1. Features Column: "features"

2. Label Column: "price"

3. Prediction Column: "predicted_price"

4. Max Depth: 5

5. Num Round: 100

6. Eta: 0.1

7. Objective: "reg:linear"


Execution:


When this node is executed, the XGBoost algorithm will train a regression model using the specified parameters. The model will then be used to predict the house prices for new data points. 


Output:


The predicted house prices will be stored in the "predicted_price" column of the output dataset.
