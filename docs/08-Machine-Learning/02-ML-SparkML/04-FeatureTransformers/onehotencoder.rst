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

ml-transformer

Class
--------- 

fire.nodes.ml.NodeOneHotEncoder

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Input columns for encoding
      * - outputCols
        - Output Columns
        - Output columns


Details
-------


 One Hot Encoder Node Details
+++++++++++++++

One-hot encoding is a process by which categorical data (such as nominal data) are converted into numerical features of a dataset. This is often a required preprocessing step since machine learning models require numerical data.

One Hot Encoder Node maps a column of label indices to a column of binary vectors, with at most a single one-value.This encoding allows algorithms which expect continuous features, such as Logistic Regression, to use categorical features.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  VARIABLES : Add the columns to be one-hot encoded
*  Input Columns : Select the categorical field in the input schema for one-hot encoding. 
*  Output Columns : Set the name of the field in the output schema that contains the binary vector result. 


Examples
-------


 One Hot Encoder Node Example
+++++++++++++++

Assume that we have the following DataFrame with column v1 as integer data type:
v1 |
---|
1  |
2  |
3  |
4  |
5  |

The output dataframe that will be obtained by selecting <b>v1</b> as the Input columns and <b>vecOut</b> as the Output column name will be :

 v1 |     vecOut    |
----|---------------|
 1  | (5,[1],[1.0]) |
 2  | (5,[2],[1.0]) |
 3  | (5,[3],[1.0]) |
 4  | (5,[4],[1.0]) |
 5  | (5,[],[])     |
 
