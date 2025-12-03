Spark ML Model Load
=========== 

Type
--------- 

ml-modelload

Class
--------- 

fire.nodes.ml.NodeModelLoad

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - selectChampionModel
        - Use Champion Model
        - Uses Champion Model For Prediction.
      * - path
        - Path To Load SparkML model
        - 
      * - fixedPath
        - Static path
        - Set this to true if you have saved the model to a static path(without UUID) while training the model.
      * - modelType
        - Model Type
        - Type of ML model to load


Details
===============
This node loads a previously saved Spark ML model into the workflow. This allows you to reuse trained models for scoring new data or further analysis.


Examples
===============
Configuration:


Output Storage Level: Choose the storage level for the loaded model.

Path: Specify the path to the saved model file. You can use the "Browse File System" button to navigate and select the model file.

Static Path: Set this to true if the model path is a static path.

Model Type: Specify the type of the model (e.g., KMeans, LogisticRegression, RandomForest).


Let's say you have trained a Spark ML model for customer churn prediction and want to save it ,


Path:data/CPG/Customer-Churn-Prediction/ModelName

Static Path:true


it would save the model at the given location with the model name,and can be used later.
