Custom Metrics
=========== 

Custom Metrics to check on aggregated field, which expects prediction, label, aggregate column and metrics.

Input
--------------
Takes Actual and Predicted Column as input

Output
--------------
Outputs Computed Metrics using Selected Metrics Type 

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.NodeCustomMetrics

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - actualCol
        - Actual Column
        - 
      * - predictedCol
        - Predicted Column
        - 
      * - metricsType
        - metricsType
        - Window Function Name
      * - posLabel
        - Positive Label for computing F1
        - Positive Label for computing F1




