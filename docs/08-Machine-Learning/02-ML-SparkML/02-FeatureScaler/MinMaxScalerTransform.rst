Min Max Scaler Transform
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

ml-predict

Class
--------- 

fire.nodes.ml.NodeMinMaxScalerTransform

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


 Min Max Scaler Transform Node Details
+++++++++++++++

The Min Max Scaler Transform Node is used to transform a dataset of Vector rows, rescaling each feature to a specific range, often [0, 1]. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Min Max Scaler Estimator Node.
The transformed DataFrame contains a new column with the scaled features.

Input Parameters
```````````````

FIT MODEL : The output of a previous Min Max Scaler Estimator Node, which contains the specified range for the transformation.


Examples
-------


 Min Max Scaler Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'features' containing continuous values. We use a Min Max Scaler Estimator Node to specify the range for the transformation, creating a fit model. Then, we use the Min Max Scaler Transform Node to transform the 'features' column using the fit model.

Input DataFrame:

id features
1 [1.0, 2.0, 3.0, 4.0]
2 [-1.0, -2.0, -3.0, -4.0]

Output

id features scaled_features
1 [1.0, 2.0, 3.0, 4.0] [0.0, 0.5, 1.0, 1.5]
2 [-1.0, -2.0, -3.0, -4.0] [-1.5, -1.0, -0.5, 0.0]
In this example, the input column is 'features' and the output column is 'scaled_features'. The fit model is created using the Min Max Scaler Estimator Node with the specified range of [0,1]. The Min Max Scaler Transform Node uses this fit model to transform the 'features' column, creating a new column 'scaled_features' with the scaled features.
