Is Not Null
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckIsNotNull

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
Is Not Null Node
---------------



Overview:
+++++++++++++++


The Is Not Null node checks if a specific column in a DataFrame contains null values. This is useful for data quality checks and ensuring data integrity.



Input:
+++++++++++++++


Column Name: The name of the column to check.



Output:
+++++++++++++++


The node will flag records where the specified column contains null values.


Examples
-------
Example:


Let's assume we have a column named name and we want to identify records where the name is null.


Configure the Node:


Column Name: name

Node Execution:


Records with a null value in the name column will be flagged.
