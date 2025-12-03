Data Drift
=========== 

This node calculates the Population Stability Index (PSI) for a set of features by comparing a reference dataset to a test dataset. It is designed to identify potential data drift in both continuous and categorical features.

Input
--------------
A reference dataset and a test dataset provided as DataFrames. The reference dataset serves as the baseline distribution, while the test dataset is used to detect any drift.

Output
--------------
A Spark DataFrame with two columns: 'feature_name' and 'psi_value'. Each row represents a feature and its corresponding PSI value, indicating the level of drift.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeDataDrift

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - A list of feature names on which the PSI will be calculated.
      * - categoricalCols
        - Categorical Columns
        - A list of features that are categorical. All other features are treated as continuous.
      * - numBins
        - Num Bins
        - The number of bins to use when binning continuous features for PSI calculation.




