Index To String
=========== 

Maps a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeIndexToString

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
        - Column containing label indices
      * - outputCol
        - Output Column
        - Output column name
      * - labels
        - Labels Column
        - eg: yes,no


Details
-------


 Index To String Node Details
+++++++++++++++

The Index To String Node is used to map a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels. It takes in a DataFrame and transforms it to another DataFrame by adding a new column containing the corresponding string values of the input column of label indices.
It takes in the parameters inputCol, outputCol and labels, which are used for input column name, output column name and user-supplied labels respectively.

Input Parameters
```````````````

INPUT COLUMN : Select the required column of label indices for mapping
OUTPUT COLUMN : The name of the output column after mapping
LABELS : The user-supplied labels for the input column of label indices


Examples
-------


 Index To String Node Example
+++++++++++++++

Consider the below <b>Index To String</b> output for the <b>label</b> column

id label string_label
0   0     dog
1   1     cat
2   2     bird

In this example, the input column is label and the output column is string_label. The index to string node maps the label column of indices back to a new column of corresponding string values. The labels provided are "dog", "cat" and "bird" and the index 0 corresponds to "dog", index 1 corresponds to "cat" and index 2 corresponds to "bird"
