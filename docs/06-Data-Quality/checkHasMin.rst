HasMin
===========

Check for min value in selected column.

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckHasMin

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
-------
Has Min Node
+++++++++++++++



Overview:
+++++++++++++++


The Has Min node checks if a specific column in a DataFrame has a minimum value. This is useful for identifying outliers or unexpected values within a dataset.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Value: The minimum value to compare against.



Output:
+++++++++++++++


The node will flag records where the specified column value is less than the defined minimum value.


Examples
-------
Example:
+++++++++++++++


Let's assume we have a column named age and we want to identify records where the age is less than 0.


Configure the Node:


Column Name: age

Value: 0

Node Execution:


Records with an age less than 0 will be flagged.
