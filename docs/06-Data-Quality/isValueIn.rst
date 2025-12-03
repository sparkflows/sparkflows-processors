Is Value In
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckIsValueIn

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
      * - values
        - Values
        - A set of objects separated by spaces used for comparison..
      * - weightage
        - Weightage
        - Weightage


Details
-------
Is Value In Node
---------------



Overview:
+++++++++++++++


The Is Value In node checks if a specific column in a DataFrame contains a value from a predefined list of values. This is useful for filtering data based on specific criteria.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Values: A list of values to check for.



Output:
+++++++++++++++


The node will flag records where the specified column value is present in the list of values.


Examples
-------
Example:


Let's assume we have a column named country and we want to identify records from specific countries.


Configure the Node:


Column Name: country

Values: USA, Canada, Mexico

Node Execution:


Records with country values of "USA", "Canada", or "Mexico" will be flagged.
