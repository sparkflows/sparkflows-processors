U Chart
=========== 

This node outputs SPC U Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcUChart

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
      * - attribute
        - Attribute Columns
        - Attribute column names
      * - subgroup
        - Subgroup Column
        - Subgroup column name
      * - identifier
        - Identifier Columns
        - Identifier column name
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


Details
-------
The U chart in Statistical Process Control (SPC) is used to monitor the number of defects per unit in a process where the sample size can vary. Unlike other control charts, the U chart accounts for different sample sizes by focusing on the defect rate rather than the absolute number of defects. It tracks the average number of defects per unit over time, making it ideal for processes with varying opportunities for defects, such as healthcare or service industries. The U chart helps detect shifts, trends, or outliers, ensuring the process remains stable and defect rates stay within control limits.


