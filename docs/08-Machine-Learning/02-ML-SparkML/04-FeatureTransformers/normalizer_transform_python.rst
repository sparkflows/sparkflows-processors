Normalizer Transform
=========== 

Normalizer is a Transformer which transforms a dataset of Vector rows, normalizing each Vector to have unit norm.

Input
--------------
It  takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It adds a new column containing the normalized value of the input column, to the incoming DataFrame.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeNormalizerTransform

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


 Normalizer Transform Node Details
+++++++++++++++

The Normalizer Transform Node is used to normalize a dataset of Vector rows by transforming each Vector to have unit norm. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Normalizer Estimator Node.
The transformed DataFrame contains a new column with the normalized values of the input column.

Input Parameters
```````````````

FIT MODEL : The output of a previous Normalizer Estimator Node, which contains the specifications for the normalization.


Examples
-------


 Normalizer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'features' containing Vector values. We use a Normalizer Estimator Node to specify the normalization, creating a fit model. Then, we use the Normalizer Transform Node to normalize the 'features' column using the fit model.

Input DataFrame:

id features
1 [1.0, 2.0, 3.0, 4.0]
2 [-1.0, -2.0, -3.0, -4.0]

Output

id features normalized_features
1 [1.0, 2.0, 3.0, 4.0] [0.18257418, 0.36514837, 0.54772256, 0.73029674]
2 [-1.0, -2.0, -3.0, -4.0] [-0.18257418, -0.36514837, -0.54772256, -0.73029674]
In this example, the input column is 'features' and the output column is 'normalized_features'. The fit model is created using the Normalizer Estimator Node. The Normalizer Transform Node uses this fit model to normalize the 'features' column, creating a new column 'normalized_features' with the normalized values.
