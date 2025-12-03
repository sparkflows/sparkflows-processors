MultiFlagOutliers
=========== 

This checks if values fall between Inter Quartile Range.

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeMultiFlagOutliers

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




Examples
-------
Example:


If you have a dataset with a "Sales" column and you set the Lower Quantile to 0.25 and the Upper Quantile to 0.75, the node will flag values below the 25th percentile as "low" outliers and values above the 75th percentile as "high" outliers.
