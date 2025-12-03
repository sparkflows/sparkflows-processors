Xbar-S Chart
=========== 

This node outputs SPC XBAR-S Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcXbarSChart

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
The XBAR-S chart is a control chart used in Statistical Process Control (SPC) to monitor the mean and variability of a process using sample data. The "XBAR" chart tracks the average (mean) of samples over time, while the "S" chart monitors the standard deviation within each sample, providing insight into process variability. This chart is ideal for larger sample sizes, typically when data is collected in subgroups. It helps detect shifts in the process mean and changes in variability, ensuring that the process remains stable and within control limits for consistent quality.


