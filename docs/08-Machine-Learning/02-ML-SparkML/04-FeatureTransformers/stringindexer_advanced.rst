String Indexer Advanced
=========== 

StringIndexer encodes a string column of labels to a column of label indices

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It adds a new column containing the encoding of the string column of labels to a column of label indices, to the incoming DataFrame.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeStringIndexerAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - handleInvalid
        - Handle Invalid
        - Invalid entries to be skipped or thrown error
      * - inputCol
        - Input Column
        - Input column for encoding
      * - outputCol
        - Output Column
        - Output column


Details
-------


 String Indexer Advanced Node Details
+++++++++++++++

The String Indexer Advanced Node is used to encode a string column of labels to a column of label indices. It takes in a DataFrame and transforms it to another DataFrame by adding a new column containing the encoding of the string column of labels to a column of label indices.
It takes in the parameters handleInvalid, inputCol and outputCol, which are used to handle invalid entries, input column name and output column name respectively.

Input Parameters
```````````````

HANDLE INVALID: Select whether to skip or throw error on invalid entries.
INPUT COLUMN: Select the required column for encoding.
OUTPUT COLUMN: The name of the output column after encoding.


Examples
-------


 String Indexer Advanced Node Example
+++++++++++++++

Consider the below <b>String Indexer Advanced</b> output for the <b>color</b> column

id color encoded_color
0   red     2
1   green   1
2   blue    0
3   purple  3

In this example, the input column is color and the output column is encoded_color. The string indexer advanced encodes the color column to a column of label indices. The handleInvalid is set to skip, so any invalid entries will be skipped.
