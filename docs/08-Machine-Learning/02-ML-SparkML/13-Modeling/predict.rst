Spark Predict
=========== 

Predict node takes in a DataFrame and Model and makes predictions

Input
--------------
It takes in a DataFrame and Model as input

Output
--------------
A new column containing the predictions is added to the input DataFrame

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodePredict

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - model_uuid
        - Model UUID
        - Enter the model uuid
      * - enablePredictionOverTimeMetrics
        - Enable Prediction Over Time Metrics
        - enable
      * - modelCategory
        - Model Category
        - Select the category


Details
===============
Predict node takes in a DataFrame and Model and makes predictions on the data using the Model.


