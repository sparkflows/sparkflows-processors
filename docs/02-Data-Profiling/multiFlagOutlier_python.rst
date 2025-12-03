MultiFlagOutliers
=========== 

This checks if values fall between Inter Quartile Range.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeMultiFlagOutliers

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Column to flag the outlier
        - The Input Column to flag the outlier
      * - lowerQuantiles
        - LowerQuantile
        - 
      * - upperQuantiles
        - UpperQuantile
        - 


Details
-------
MultiFlagOutliers Node

Overview:


This node is designed to identify and flag outliers in a dataset based on specified quantile ranges. It helps to detect anomalies and anomalies that deviate significantly from the norm.


Configuration:


Input Column to Flag the Outlier: Select the column containing the numeric values to be analyzed.

Lower Quantile: Set the lower quantile threshold (e.g., 0.05 for the 5th percentile).

Upper Quantile: Set the upper quantile threshold (e.g., 0.95 for the 95th percentile).


Examples
-------
Example:


If you have a dataset with a "Sales" column and you set the Lower Quantile to 0.25 and the Upper Quantile to 0.75, the node will flag values below the 25th percentile as "low" outliers and values above the 75th percentile as "high" outliers.
