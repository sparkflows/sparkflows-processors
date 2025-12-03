IMR-R Chart
=========== 

This node outputs SPC IMR-R Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcIMRRChart

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - title
        - Title
        - 
      * - titleColor
        - Title Color
        - 
      * - description
        - Description
        - 
      * - descriptionColor
        - Description Color
        - 
      * - measurements
        - Measurements Columns
        - Measurements column names
      * - identifier
        - Identifier Columns
        - Identifier column names
      * - test1
        - point beyond the control limits
        - 
      * - test2
        - k or more consecutive points are one side of the centerline
        - 
      * - test3
        - k or more consecutive points are increasing or decreasing
        - 
      * - test4
        - k consecutive points alternate up or down
        - 
      * - test5
        - k out of k+1 consecutive points are one side of the centerline
        - 
      * - test6
        - k out of n consecutive points are one side of the centerline
        - 


Details
===============
The I-MR-R chart in Statistical Process Control (SPC) is a variation of the I-MR chart, designed for monitoring individual measurements and ranges across subgroups. The "I" chart tracks individual data points, the "MR" chart monitors the moving range between consecutive points, and the "R" chart shows the range within subgroups, helping to detect variability. This chart is useful when dealing with processes where subgroup size is small or where both individual observations and subgroup variation need monitoring. It helps ensure process stability by identifying shifts, trends, and variability, ensuring the process stays within control limits.


