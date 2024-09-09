Quantile Discretizer Transform
=========== 

QuantileDiscretizer takes a column with continuous features and outputs a column with binned categorical features.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output DataFrame contains a new column of binned categorical features.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodeQuantileDiscretizerTransform

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


 Quantile Discretizer Transform Node Details
+++++++++++++++

The Quantile Discretizer Transform Node is used to discretize a continuous feature into a categorical feature by specifying a set of boundaries. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Quantile Discretizer Estimator Node.
The transformed DataFrame contains a new column with the binned categorical features.

Input Parameters
```````````````

FIT MODEL : The output of a previous Quantile Discretizer Estimator Node, which contains the specified boundaries for the discretization.


Examples
-------


 Quantile Discretizer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'age' containing continuous values. We use a Quantile Discretizer Estimator Node to specify the boundaries for the discretization, creating a fit model. Then, we use the Quantile Discretizer Transform Node to discretize the 'age' column using the fit model.

Input DataFrame:

id age
1 22
2 35
3 45
4 55

Output

id age age_binned
1 22 1
2 35 2
3 45 3
4 55 4
In this example, the input column is 'age' and the output column is 'age_binned'. The fit model is created using the Quantile Discretizer Estimator Node. The Quantile Discretizer Transform Node uses this fit model to discretize the 'age' column, creating a new column 'age_binned' with the binned categorical features.
