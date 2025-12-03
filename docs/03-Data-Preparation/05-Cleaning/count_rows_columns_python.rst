Count rows columns
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeCountRowsColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - variable
        - Variable Name
        - Name of the Variable in which the count is stored


Details
-------
Count Rows and Columns Node
---------------



Overview:
+++++++++++++++


The Count Rows and Columns node counts the number of rows and columns in a DataFrame. This information can be useful for understanding the size and structure of your data.



Input:
+++++++++++++++


None



Output:
+++++++++++++++


Variable Name: The name of the variable that will store the count of rows and columns.


Examples
-------
Example:


Let's assume we have a DataFrame with 100 rows and 5 columns.


Configure the Node:


Variable Name: count

Node Execution:


The node will count the rows and columns in the DataFrame.

The variable count will store a value like [100, 5].
