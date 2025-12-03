Is Primary Key
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckPrimaryKey

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
Is Primary Key Node
---------------



Overview:
+++++++++++++++


The Is Primary Key node checks if a specific column in a DataFrame is a primary key. This is useful for data quality checks and ensuring data integrity.



Input:
+++++++++++++++


Column Name: The name of the column to check.



Output:
+++++++++++++++


The node will flag records where the specified column contains duplicate values.


Examples
===============
Example:
---------------


Let's assume we have a column named id and we want to ensure it has unique values.


Configure the Node:


Column Name: id

Node Execution:


Records with duplicate values in the id column will be flagged.
