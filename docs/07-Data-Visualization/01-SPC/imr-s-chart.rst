IMR-S Chart
=========== 

This node outputs SPC IMR-S Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcIMRSChart

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
-------
The I-MR-S chart in Statistical Process Control (SPC) is a control chart used to monitor both individual measurements and the variability within subgroups. The "I" chart tracks individual data points over time, the "MR" chart monitors the moving range between consecutive measurements, and the "S" chart measures the standard deviation within subgroups. This chart is ideal for processes with small sample sizes and helps detect shifts in both the process mean and variability. By identifying trends, shifts, or outliers, the I-MR-S chart ensures that a process remains stable and operates within control limits for consistent quality.


