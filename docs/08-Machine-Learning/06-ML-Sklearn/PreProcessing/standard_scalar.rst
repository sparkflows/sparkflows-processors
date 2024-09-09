Sklearn StandardScalar
=========== 

Standardizing a dataset involves rescaling the distribution of values so that the mean of observed values is 0 and the standard deviation is 1.

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeStandardScalarFitTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - with_mean
        - With Mean
        - 
      * - with_std
        - With Std
        - 


Details
-------


 Sklearn Standard Scalar Node Details
+++++++++++++++

The Sklearn Standard Scalar Node is used to standardize a dataset. Standardizing a dataset involves rescaling the distribution of values so that the mean of observed values is 0 and the standard deviation is 1. It takes in the input data and applies the standardization to the features. The input data can be in the form of a numpy array or a pandas DataFrame.
It also takes 2 parameters: with_mean and with_std.

with_mean: If it is set to true, it will center the data before scaling.
with_std: If it is set to true, it will scale the data to unit variance (or equivalently, unit standard deviation).

Input Parameters
```````````````

WITH MEAN : If it is set to true, it will center the data before scaling.
WITH STD : If it is set to true, it will scale the data to unit variance (or equivalently, unit standard deviation).


Examples
-------


 Sklearn Standard Scalar Node Example
+++++++++++++++

Consider the below <b>Sklearn Standard Scalar</b> output for the <b>features</b> column

id features scaled_features
0 [1.0, 2.0, 3.0, 4.0] [-1.34, -0.67, 0.0, 0.67]
1 [-1.0, -2.0 1, -3.0, -4.0] [1.34, 0.67, 0.0, -0.67]

In this example, the input column is features and the output column is scaled_features. The with_mean parameter is set to true and with_std parameter is set to false. The Standard Scaler will center the data before scaling, so the mean of the features column is 0. The standard deviation is not scaled, so it is not equal to 1.

Another example, if the with_mean parameter is set to false and with_std parameter is set to true. The Standard Scaler will not center the data but it will scale the data to unit variance (or equivalently, unit standard deviation)
