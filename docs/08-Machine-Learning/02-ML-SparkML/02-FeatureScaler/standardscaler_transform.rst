Standard Scaler Transform
=========== 

StandardScaler transforms a dataset of Vector rows, normalizing each feature to have unit standard deviation and/or zero mean.

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
It adds a new column containing the transform of the input Vector column to unit standard deviation and/or zero mean features to the incoming DataFrame.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodeStandardScalerTransform

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


 Standard Scaler Transform Node Details
+++++++++++++++

The Standard Scaler Transform Node is used to normalize a dataset of Vector rows, by transforming each feature to have unit standard deviation and/or zero mean. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Standard Scaler Estimator Node.
The transformed DataFrame contains a new column with the transformed features.

Input Parameters
```````````````

FIT MODEL : The output of a previous Standard Scaler Estimator Node, which contains the specifications for the transformation.


Examples
-------


 Standard Scaler Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'features' containing continuous values. We use a Standard Scaler Estimator Node to specify the transformation, creating a fit model. Then, we use the Standard Scaler Transform Node to transform the 'features' column using the fit model.

Input DataFrame:

id features
1 [1.0, 2.0, 3.0, 4.0]
2 [-1.0, -2.0, -3.0, -4.0]

Output

id features scaled_features
1 [1.0, 2.0, 3.0, 4.0] [-1.34164079, -0.4472136, 0.4472136, 1.34164079]
2 [-1.0, -2.0, -3.0, -4.0] [-1.34164079, -1.34164079, -1.34164079, -1.34164079]
In this example, the input column is 'features' and the output column is 'scaled_features'. The fit model is created using the Standard Scaler Estimator Node. The Standard Scaler Transform Node uses this fit model to transform the 'features' column, creating a new column 'scaled_features' with the transformed features.
