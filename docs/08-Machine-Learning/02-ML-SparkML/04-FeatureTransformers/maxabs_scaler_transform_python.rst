MaxAbs Scaler Transform
=========== 

Rescale each feature individually to range [-1, 1] by dividing through the largest maximum absolute value in each feature.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeMaxAbsScalerTransform

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


 MaxAbs Scaler Transform Node Details
+++++++++++++++

The MaxAbs Scaler Transform Node is used to rescale a dataset of Vector rows individually feature-wise to the given range [-1, 1]. It rescales each feature individually by dividing through the largest maximum absolute value in each feature. It also takes in a fit model as input, which is typically the output of a previous MaxAbs Scaler Estimator Node.
The transformed DataFrame contains a new column with the scaled features.

Input Parameters
```````````````

FIT MODEL : The output of a previous MaxAbs Scaler Estimator Node, which contains the maximum absolute value for the transformation.


Examples
-------


 MaxAbs Scaler Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'features' containing continuous values. We use a MaxAbs Scaler Estimator Node to specify the maximum absolute value for the transformation, creating a fit model. Then, we use the MaxAbs Scaler Transform Node to transform the 'features' column using the fit model.

Input DataFrame:

id features
1 [1.0, 2.0, 3.0, 4.0]
2 [-1.0, -2.0, -3.0, -4.0]

Output

id features scaled_features
1 [1.0, 2.0, 3.0, 4.0] [0.25, 0.5, 0.75, 1.0]
2 [-1.0, -2.0, -3.0, -4.0] [-0.25, -0.5, -0.75, -1.0]

In this example, the input column is 'features' and the output column is 'scaled_features'. The fit model is created using the MaxAbs Scaler Estimator Node. The MaxAbs Scaler Transform Node uses this fit model to transform the 'features' column, creating a new column 'scaled_features' with the scaled features.
