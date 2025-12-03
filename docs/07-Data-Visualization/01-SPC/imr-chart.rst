I-MR Chart
===========

This node outputs SPC IMR Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcIMRChart

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
The I-MR (Individual-Moving Range) chart in Statistical Process Control (SPC) monitors process stability using individual data points. The "I" chart tracks individual measurements over time, while the "MR" chart shows the moving range between consecutive measurements to detect variability. It's ideal when sample sizes are small or when it's difficult to collect multiple measurements. By identifying shifts, trends, or outliers, the I-MR chart helps ensure that a process stays within control limits and operates consistently, making it a key tool for maintaining quality control in manufacturing and other processes.


