C Chart
=========== 

This node outputs SPC C Chart and performs control tests.

Type
--------- 

SPC-Chart

Class
--------- 

fire.nodes.graph.NodeSpcCChart

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
===============
The C chart in Statistical Process Control (SPC) is used to monitor the count of defects in a process when the sample size remains constant. It tracks the total number of defects or non-conformities in each sample, making it suitable for processes where multiple defects can occur in a single unit, such as manufacturing or inspection processes. The C chart helps identify trends, shifts, or out-of-control points by assessing the variation in defect counts. By ensuring that defect counts stay within control limits, the C chart helps maintain process stability and supports consistent quality management.


