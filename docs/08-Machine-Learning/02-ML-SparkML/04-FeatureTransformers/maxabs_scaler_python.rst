MaxAbs Scaler
=========== 

Rescale each feature individually to range [-1, 1] by dividing through the largest maximum absolute value in each feature.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeMaxAbsScaler

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
        - Column containing input
      * - outputCol
        - Output Column
        - Output column names


Details
-------


 MaxAbs Scaler Node Details
+++++++++++++++

The MaxAbs Scaler Node is used to rescale a dataset individually feature-wise to the given range [-1, 1]. It rescales each feature individually to range [-1, 1] by dividing through the largest maximum absolute value in each feature.
It takes in the common parameters inputCol and outputCol, which are the input and output column names. The input column should be in the format of VectorUDT.

Input Parameters
```````````````

INPUT COLUMN : Select the required column for which scaling has to be done .
OUTPUT COLUMN : The name of the output column after scaling.


Examples
-------


 MaxAbs Scaler Node Example
+++++++++++++++

Consider the below <b>MaxAbs Scaler</b> output for the <b>features</b> column

id	features	scaled_features
0	[1.0, 2.0, 3.0, 4.0]	[0.25, 0.5, 0.75, 1.0]
1	[-1.0, -2.0, -3.0, -4.0]	[-0.25, -0.5, -0.75, -1.0]
In this example, the input column is features and the output column is scaled_features. The maxabs scaler scales the features individually to the range [-1, 1],by dividing through the largest maximum absolute value in each feature. Here the largest absolute value is 4.0 so the features are divided by 4.0.
