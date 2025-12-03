HasMax
=========== 

Check for max value in selected column.

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckHasMax

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Column Name
        - The column name.
      * - values
        - Values
        - A set of objects separated by spaces used for comparison..
      * - weightage
        - Weightage
        - Weightage


Details
===============
Has Max Node
---------------



Overview:
+++++++++++++++


The Has Max node checks if a specific column in a DataFrame has a maximum value. This is useful for identifying outliers or unexpected values within a dataset.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Value: The maximum value to compare against.



Output:
+++++++++++++++


The node will flag records where the specified column value is greater than the defined maximum value.


Examples
===============
Example:


Let's assume we have a column named age and we want to identify records where the age is greater than 120.


Configure the Node:


Column Name: age

Value: 120

Node Execution:


Records with an age greater than 120 will be flagged.
