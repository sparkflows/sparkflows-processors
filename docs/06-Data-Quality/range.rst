ColumnValuesToBeBetween
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckColumnValuesToBeBetween

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
      * - min
        - Min
        - The minimum value of column.
      * - max
        - Max
        - The Maximum value of range
      * - weightage
        - Weightage
        - Weightage


Details
===============
Column Values To Be Between Node
---------------



Overview:
+++++++++++++++


The Column Values To Be Between node checks if the values in a specific column are within a specified range. This is useful for data quality checks and ensuring data integrity.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Min: The minimum allowed value.

Max: The maximum allowed value.



Output:
+++++++++++++++


The node will flag records where the specified column value is outside the defined range.


Examples
===============
Example:


Let's assume we have a column named age and we want to identify records where the age is less than 0 or greater than 120.


Configure the Node:


Column Name: age

Min: 0

Max: 120

Node Execution:


Records with an age less than 0 or greater than 120 will be flagged.
