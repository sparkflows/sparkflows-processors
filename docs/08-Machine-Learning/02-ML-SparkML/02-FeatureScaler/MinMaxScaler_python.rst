Min Max Scaler
=========== 

MinMaxScaler transforms a dataset of Vector rows, rescaling each feature to a specific range (often [0, 1])

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
A new column containing the scaled features is added to the incoming DataFrame

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeMinMaxScaler

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
        - The input column name
      * - outputCol
        - Output Column
        - The output column name
      * - max
        - Max
        - The upper bound after transformation, shared by all features
      * - min
        - Min
        - The lower bound after transformation, shared by all features


Details
-------


 Min Max Scaler Transform Node Details
+++++++++++++++

The Min Max Scaler Transform Node is used to rescale a dataset of Vector rows by transforming each feature to a specific range, often [0, 1]. It takes no additional parameter other than the input DataFrame and the output column name.

It rescales each feature individually to a specific range by dividing through the largest minimum-maximum value in each feature and it adds a new column to the DataFrame with the scaled feature values.

Input Parameters
```````````````

INPUT DATAFRAME: The dataframe containing the feature column to be transformed.
OUTPUT COLUMN : The name of the output column after rescaling.


Examples
-------


 Min Max Scaler Transform Node Example
+++++++++++++++

Consider the below <b>Min Max Scaler</b> output for the <b>features</b> column

id features scaled_features
0 [1.0, 2.0, 3.0, 4.0] [0.0, 0.33, 0.67, 1.0]
1 [-1.0, -2.0, -3.0, -4.0] [0.0, 0.33, 0.67, 1.0]
In this example, the input column is features and the output column is scaled_features. The minmax scaler scales the features individually to the range [0,1],by dividing through the largest minimum-maximum value in each feature. Here the minimum value is -4.0 and the maximum value is 4.0 so the features are divided by (4.0 - (-4.0)) = 8.0.
