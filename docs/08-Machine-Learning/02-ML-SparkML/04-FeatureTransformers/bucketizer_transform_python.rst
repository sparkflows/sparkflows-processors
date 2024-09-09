Bucketizer Transform
=========== 

Bucketizer Transform

Input
--------------
It  takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output column contains the bucket index for each value in the input column.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeBucketizerTransform

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


 Bucketizer Transform Node Details
+++++++++++++++

The Bucketizer Transform Node is used to transform a continuous feature into a categorical feature by specifying a set of boundaries. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Bucketizer Estimator Node.
The transformed DataFrame contains a new column with the bucket index for each value in the input column.

Input Parameters
```````````````

FIT MODEL : The output of a previous Bucketizer Estimator Node, which contains the specified boundaries for the transformation.


Examples
-------


 Bucketizer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'age' containing continuous values. We use a Bucketizer Estimator Node to specify the boundaries for the transformation, creating a fit model. Then, we use the Bucketizer Transform Node to transform the 'age' column using the fit model.

Input DataFrame:

id	age
1	22
2	35
3	45
4	55

Output

id	age	age_bucket
1	22	0
2	35	1
3	45	2
4	55	3
In this example, the input column is 'age' and the output column is 'age_bucket'. The fit model is created using the Bucketizer Estimator Node. The Bucketizer Transform Node uses this fit model to transform the 'age' column, creating a new column 'age_bucket' with the bucket index for each value in the 'age' column.
