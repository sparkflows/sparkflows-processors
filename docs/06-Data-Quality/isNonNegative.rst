IsNonNegative
=========== 

Should not contain negative values

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckIsNonNegative

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - cols
        - Column Name
        - The column name.
      * - weightage
        - Weightage
        - Weightage


Details
===============
IsNonNegative Node
---------------



Overview:
+++++++++++++++


The IsNonNegative node checks if a specific column in a DataFrame contains only non-negative values. This is useful for data quality checks and ensuring data integrity.



Input:
+++++++++++++++


Column Name: The name of the column to check.



Output:
+++++++++++++++


The node will flag records where the specified column contains negative values.


Examples
===============
Example:
---------------


Let's assume we have a column named age and we want to identify records where the age is negative.


Configure the Node:


Column Name: age

Node Execution:


Records with an age less than 0 will be flagged.
