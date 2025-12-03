Sklearn Predict
===========

Predict node takes in a dataframe and model and makes predictions

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

fire.nodes.sklearn.NodeSklearnPredict

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - featureCols
        - Feature Columns
        - Features used while Training. Can be kept empty for Supervised Models
      * - targetCol
        - Target Column
        - The label column for model fitting
      * - keyCol
        - Key Column
        - The key column to identify the each row/data/sample.




