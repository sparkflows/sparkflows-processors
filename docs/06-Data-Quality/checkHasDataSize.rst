HasDataSize
=========== 

Check the size of the dataset.

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckHasDataSize

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
      * - checkTypes
        - CheckTypes
        - 
      * - values
        - Values
        - 
      * - weightage
        - Weightage
        - Weightage


Details
-------
Has Data Size Node
---------------



Overview:
+++++++++++++++


The Has Data Size node checks if a specific column in a DataFrame has a non-zero data size. This is useful for filtering out rows or columns with empty or null values.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Check Types: The type of check to perform (e.g., null, empty, zero).

Values: Specific values to check for (if applicable).


Output:
+++++++++++++++


The node will filter out rows where the specified column meets the defined condition.


Examples
-------
Example:


Let's assume we have a DataFrame with a column named amount. We want to filter out rows where amount is null or zero.


Configure the Node:


Column Name: amount

Check Types: Null, Zero

Values: (Leave blank)

Node Execution:


Rows with amount = null or amount = 0 will be filtered out.
