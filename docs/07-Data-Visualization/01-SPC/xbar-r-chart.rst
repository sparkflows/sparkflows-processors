Xbar-R Chart
=========== 

This node outputs SPC XBAR-R Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcXbarRChart

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
The XBAR-R chart is a control chart in Statistical Process Control (SPC) used to monitor the process mean and variability using small sample sizes. The "XBAR" chart tracks the average (mean) of samples over time, while the "R" chart monitors the range (difference between the highest and lowest values) within each sample, reflecting process variability. It is most effective when sample sizes are small (typically 2 to 10 units per subgroup). The XBAR-R chart helps identify shifts in the process mean and changes in variability, ensuring the process remains stable and under control for consistent quality.


