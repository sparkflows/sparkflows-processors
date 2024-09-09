Quantile Discretizer
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

ml-estimator

Class
--------- 

fire.nodes.ml.NodeQuantileDiscretizer

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
        - The Input column name
      * - outputCol
        - Output Column
        - Output column name
      * - numBuckets
        - NumBuckets
        - Maximum number of buckets (quantiles or categories) into which the data points are grouped. Must be >= 2.


Details
-------


 Quantile Discretizer Node Details
+++++++++++++++

The Quantile Discretizer Node is used to convert a column with continuous features to a column with binned categorical features. It takes in a DataFrame and transforms it to another DataFrame with a new column of binned categorical features.
It takes in the parameters inputCol, outputCol and numBuckets, which are the input column name, output column name and maximum number of buckets respectively. The input column should be in the format of Double.

Input Parameters
```````````````

INPUT COLUMN: Select the required column for which discretization has to be done.
OUTPUT COLUMN: The name of the output column after discretization.
NUMBUCKETS : Maximum number of buckets (quantiles or categories) into which the data points are grouped. Must be >= 2.


Examples
-------


 Quantile Discretizer Node Example
+++++++++++++++

Consider the below <b>Quantile Discretizer</b> output for the <b>age</b> column

id age age_bucket
0   20   1
1   25   1
2   30   2
3   35   2

In this example, the input column is age and the output column is age_bucket. The quantile discretizer takes the column age and converts it to age_bucket by grouping the data points into 2 buckets. The value of numBuckets is 2, so the data points are grouped into 2 buckets.
