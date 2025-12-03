XGBoost Classifier
=========== 



Input
--------------
It takes in a DataFrame as input and performs XGBoost Classification

Output
--------------
The XGBoost Model generated is passed along to the next nodes. The input DataFrame is also passed along to the next nodes

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeXGBoostClassifier

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
      * - numClass
        - Num Class
        - 
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
===============
Deatils: https://xgboost.readthedocs.io/en/latest/jvm/xgboost4j_spark_tutorial.html#xgboost4j-spark-tutorial-version-0-9



XGBoost Classifier Node Details
---------------


This node implements the XGBoost algorithm for classification tasks. It can be used for a variety of classification problems, including binary classification (e.g., spam detection) and multi-class classification (e.g., image recognition).


Key Parameters:


Features Column: The name of the column containing the features used for training.

Label Column: The name of the column containing the target variable to be predicted.

Prediction Column: The name of the column where the predicted class probabilities will be stored.

Num Class: The number of classes in the classification problem.

Max Depth: The maximum depth of each tree in the ensemble. Higher values can lead to overfitting.

Max Bins: The maximum number of bins to use for histogram-based approximations.

Max Leaves: The maximum number of leaves per tree.

Num Round: The number of boosting rounds (trees) to build.

Num Workers: The number of threads to use for parallel processing.

Objective: The objective function to optimize. 'multi:softprob' is used for multi-class classification.

Eta: The learning rate, which controls the step size at each boosting round.


Examples
===============
XGBoost Classifier Node Example
---------------


Scenario:


Let's assume we have a dataset containing information about customers, including features like age, income, purchase history, etc., and the corresponding target variable being the customer's preferred product category.


Configuration:


1. Features Column: "customer_features"

2. Label Column: "product_category"

3. Prediction Column: "predicted_probabilities"

4. Num Class: 3 (assuming three product categories)

5. Max Depth: 6

6. Num Round: 100

7. Eta: 0.3

8. Objective: "multi:softprob"


Execution:


When this node is executed, the XGBoost algorithm will train a classification model using the specified parameters. The model will then be used to predict the probabilities of each product category for new customer data points. 


Output:


The predicted probabilities for each product category will be stored in the "predicted_probabilities" column of the output dataset. This column will likely be a list or array containing the probabilities for each class.
