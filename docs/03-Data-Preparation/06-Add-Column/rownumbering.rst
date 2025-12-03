Row Numbering
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRowNumbering

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCol
        - Output Column
        - Name for output column


Details
===============
Row Numbering Node
---------------



Overview:
+++++++++++++++


The Row Numbering node adds a new column to a DataFrame, assigning a unique row number to each row. This can be useful for various data processing tasks, such as tracking row order or identifying specific rows.



Input:
+++++++++++++++


None



Output:
+++++++++++++++


Output Column: The name of the new column to store the row numbers.


Examples
===============
Example:
---------------


Let's assume we have a DataFrame with the following data:


id    column1    column2

1    A    10

2    B    20

3    C    30


Configure the Node:


Output Column: row_id

Node Execution:


The node will add a new column row_id to the DataFrame, assigning sequential numbers to each row:


id    column1    column2    row_id

1    A    10    1

2    B    20    2

3    C    30    3
