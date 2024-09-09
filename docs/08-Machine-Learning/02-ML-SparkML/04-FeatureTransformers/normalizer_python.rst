Normalizer
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

ml-estimator

Class
--------- 

fire.nodes.etl.NodeNormalizer

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
      * - p
        - P
        - Normalization in L^p space. Must be >= 1. (default: p = 2)


Details
-------


 Normalizer Node Details
+++++++++++++++

The Normalizer node is a Transformer which transforms a dataset of Vector rows, normalizing each Vector to have unit norm. It takes parameter p, which specifies the p-norm used for normalization. (p=2 by default.)
This normalization can help standardize your input data and improve the behavior of learning algorithms.

When you don’t know the distribution of your data or when you know it’s not Gaussian, normalization is a smart approach to apply. Normalization is useful when your data has variable scales and the technique you’re employing, such as k-nearest neighbors and artificial neural networks, doesn’t make assumptions about the distribution of your data.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  Input Column : Select the column in the input schema that contains the features.
*  Output Column : Set the name of the field in the output schema that contains the normalized features.
*  P : The p-norm to use for normalization. Supported values are '1' and '2'. Default is 2.


Examples
-------


 Normalizer Node Example
+++++++++++++++

Consider the below dataset which contains two columns, id & features.


| id  |   features    |
|:---:|:--------------|
| 0   |[1.0,0.5,-1.0] |
| 1   |[2.0,1.0,1.0]  |
| 2   |[4.0,10.0,2.0] |

Applying <b>Normalizer</b> node with <b>features</b> as the input column and <b>normFeatures</b> as the output column, we should get the following dataframe as output:

| id  |   features    |   normFeatures    |
|:---:|:--------------|:------------------|
| 0   |[1.0,0.5,-1.0] | [1.0,0.5,-1.0]    |
| 1   | [2.0,1.0,1.0] | [1.0,0.5,0.5]     |
| 2   |[4.0,10.0,2.0] | [0.4,1.0,0.2]     |
|:---:|:--------------|:------------------|
