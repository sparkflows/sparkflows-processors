One Hot Encoder
=========== 

Maps a column of label indices to a column of binary vectors, with at most a single one-value

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output DataFrame contains a new column which contains the mapping of a column of label indices to a column of binary vectors, with at most a single one-value.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeOneHotEncoder

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCol
        - Input Column
        - Input column for encoding
      * - outputCol
        - Output Column
        - Output column


Details
-------


 One Hot Encoder Node Details
+++++++++++++++

The One Hot Encoder Node maps a column of label indices to a column of binary vectors, with at most a single one-value. It is an Estimator that takes in a DataFrame and transforms it to another DataFrame.
It takes in the common parameters inputCol and outputCol, which are the input and output column names. The input column should be of the type Integer, Long, Double or Float.

Input Parameters
```````````````

INPUT COLUMN : Select the required column for which one-hot encoding has to be done.
OUTPUT COLUMN : The name of the output column after encoding.


Examples
-------


 One Hot Encoder Node Example
+++++++++++++++

Consider the below <b>One Hot Encoder </b> output for the <b>color</b> column

id	color	encoded_color
0	Red	[1.0, 0.0, 0.0]
1	Blue	[0.0, 1.0, 0.0]
2	Green	[0.0, 0.0, 1.0]
In this example, the input column is color and the output column is encoded_color. The One Hot Encoder  maps the column color to a column of binary vectors, with at most a single one-value. Each unique category in the input column will be mapped to a binary vector of the same length as the number of unique categories in the input column.
