EWMA Chart
=========== 

This node outputs SPC EWMA Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcEWMAChart

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
      * - weight
        - Weight
        - 
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
The EWMA (Exponentially Weighted Moving Average) chart is a control chart in Statistical Process Control (SPC) used to monitor process performance by giving more weight to recent data points. Unlike traditional control charts that treat all data equally, the EWMA chart emphasizes the latest observations, making it highly sensitive to small shifts in the process mean. This makes it ideal for detecting gradual trends or drifts in the process. The EWMA chart is particularly useful in processes where maintaining tight control over small variations is critical, such as in continuous manufacturing or quality-sensitive industries.


