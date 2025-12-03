ML Data Metrics
===========

This node calculates and outputs feature statistics and data drift metrics—including PSI and drift flags—by comparing a baseline dataset with a new batch dataset

Type
--------- 

transform

Class
--------- 

fire.nodes.util.NodeMLModelMetrics

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
      * - features
        - Numeric Columns
        - Features to be used for computing metrics
      * - categorical_features
        - Categorical Columns
        - Categorical Features to be used for computing metrics




