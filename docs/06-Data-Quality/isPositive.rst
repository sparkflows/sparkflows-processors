IsPositive
===========



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckIsPositive

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
-------
Is Positive Node
+++++++++++++++



Overview:
+++++++++++++++


The Is Positive node checks if a specific column in a DataFrame contains only positive values. This is useful for data quality checks and ensuring data integrity.



Input:
+++++++++++++++


Column Name: The name of the column to check.



Output:
+++++++++++++++


The node will flag records where the specified column contains negative or zero values.


Examples
-------
Example:


Let's assume we have a column named age and we want to identify records where the age is negative or zero.


Configure the Node:


Column Name: age

Node Execution:


Records with an age less than or equal to 0 will be flagged.
