One Hot Encoder Advanced Transform
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

ml-predict

Class
--------- 

fire.nodes.ml.NodeOneHotEncoderAdvancedTransform

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


 One Hot Encoder Advanced Transform Node Details
+++++++++++++++

The One Hot Encoder Advanced Transform Node is used to map a column of label indices to a column of binary vectors, with at most a single one-value. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous One Hot Encoder Advanced Estimator Node.
The transformed DataFrame contains a new column with the mapping of a column of label indices to a column of binary vectors, with at most a single one-value.

Input Parameters
```````````````

FIT MODEL : The output of a previous One Hot Encoder Advanced Estimator Node, which contains the information about the column to be encoded and the specifications for the encoding.


Examples
-------


 One Hot Encoder Advanced Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'color' containing categorical values. We use a One Hot Encoder Advanced Estimator Node to specify the column to be encoded and the specifications for the encoding, creating a fit model. Then, we use the One Hot Encoder Advanced Transform Node to transform the 'color' column using the fit model.

Input DataFrame:

id color
1 red
2 green
3 blue

Output

id color color_encoded
1 red [1.0, 0.0, 0.0]
2 green [0.0, 1.0, 0.0]
3 blue [0.0, 0.0, 1.0]
In this example, the input column is 'color' and the output column is 'color_encoded'. The fit model is created using the One Hot Encoder Advanced Estimator Node. The One Hot Encoder Advanced Transform Node uses this fit model to transform the 'color' column, creating a new column 'color_encoded' with the binary vectors of the encoded values.
