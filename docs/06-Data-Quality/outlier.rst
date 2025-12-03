CheckOutliers
===========

This checks if values fall between Inter Quartile Range.

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckOutliers

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
        - LowerQuartile
        - 
      * - upperQuantiles
        - UpperQuartile
        - 
      * - weightage
        - Weightage
        - Weightage


Details
-------
Check Outliers Node
+++++++++++++++



Overview:
+++++++++++++++


The Check Outliers node identifies outliers in a specified column using the Interquartile Range (IQR) method. Outliers are defined as values that fall below the lower quartile minus 1.5 times the IQR or above the upper quartile plus 1.5 times the IQR.



Input:
+++++++++++++++


Input Column to Flag the Outlier: The name of the column to check for outliers.

Lower Quartile: The lower quartile value (optional, can be calculated automatically).

Upper Quartile: The upper quartile value (optional, can be calculated automatically).



Output:
+++++++++++++++


The node will flag records that are identified as outliers.


Examples
-------
Example:


Let's assume we have a column named age and we want to identify outliers based on the IQR method.


Configure the Node:


Input Column to Flag the Outlier: age

Node Execution:


The node will calculate the lower and upper quartiles of the age column.

Records with age values outside the IQR range will be flagged as outliers.
