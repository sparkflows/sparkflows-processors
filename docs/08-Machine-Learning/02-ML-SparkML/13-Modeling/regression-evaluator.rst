Regression Evaluator
=========== 

Evaluator for regression, which expects two input columns: prediction and label.

Input
--------------
It takes in a DataFrame as input

Output
--------------
The incoming DataFrame is passed to the output

Type
--------- 

ml-evaluator

Class
--------- 

fire.nodes.ml.NodeRegressionEvaluator

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - labelCol
        - Label Column
        - The label column for model fitting.
      * - predictionCol
        - Prediction Column
        - The prediction column.


Details
-------


Evaluator for regression, which expects two input columns: prediction and label.

More details are available at Apache Spark ML docs page:

https://spark.apache.org/docs/latest/api/java/org/apache/spark/ml/evaluation/RegressionEvaluator.html


