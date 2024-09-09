Bucketizer
=========== 

The Bucketizer transformer in PySpark is used to discretize continuous features into categorical ones by creating a fixed number of buckets.

Input
--------------
It  takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output column contains the bucket index for each value in the input column.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeBucketizer

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
      * - splits
        - splits
        - eg : [float("-inf"), -0.5, 0.0, 0.5, float("inf")]


Details
-------


 Bucketizer Node Details
+++++++++++++++

The Bucketizer Node is used to discretize continuous features into categorical ones by creating a fixed number of buckets. It takes in a DataFrame and transforms it to another DataFrame by adding a new column containing the bucket index for each value in the input column.
It takes in the parameters inputCol, outputCol and splits, which are used for input column name, output column name and the splits for the buckets respectively.

Input Parameters
```````````````

INPUT COLUMN : Select the required continuous column for discretization
OUTPUT COLUMN : The name of the output column after discretization
SPLITS : The splits for the buckets, specified as an array of floats.


Examples
-------


 Bucketizer Node Example
+++++++++++++++

Consider the below <b>Bucketizer</b> output for the <b>age</b> column with splits [-inf, 20, 30, 40, inf]

id age bucket
0   10  0
1   25  2
2   35  3
3   50  4

In this example, the input column is age and the output column is bucket. The bucketizer discretizes the continuous feature age into categorical ones by creating 4 buckets. The splits for the buckets are [-inf, 20, 30, 40, inf] and the values less than 20 belongs to bucket 0, values between 20 and 30 belongs to bucket 1 and so on.
