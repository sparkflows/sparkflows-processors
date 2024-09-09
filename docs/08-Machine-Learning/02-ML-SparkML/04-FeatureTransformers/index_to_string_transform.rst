Index To String Transform
=========== 

Maps a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeIndexToStringTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description


Details
-------


 Index To String Transform Node Details
+++++++++++++++

The Index To String Transform Node is used to map a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels.
It takes in a fit model as input, which is typically the output of a previous StringIndexer Estimator Node, and uses it to map the indices back to their original string values in a DataFrame.

Input Parameters
```````````````

FIT MODEL : The output of a previous StringIndexer Estimator Node, which contains the index-string mapping used for converting the string values back to their original indices.


Examples
-------


 Index To String Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'gender' containing indexed values. We use a StringIndexer Estimator Node to convert the 'gender' column to indexed values and create a fit model. Then, we use the Index To String Transform Node to convert the indexed values back to their original string values in the 'gender' column using the fit model.

Input DataFrame:

id	gender
1	0
2	1
3	0
4	1
StringIndexer Estimator Node:
Input column = 'gender'
Output column = 'gender_index'

Index To String Transform Node:
Input = DataFrame, Fit Model
Output =

id	gender
1	'male'
2	'female'
3	'male'
4	'female'
In this example, the input DataFrame contains indexed values in the 'gender' column. The fit model is created using the StringIndexer Estimator Node. The Index To String Transform Node uses this fit model to convert the indexed values back to their original string values in the 'gender' column.
