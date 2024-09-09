Sklearn Normalizer
=========== 

Normalize samples individually to unit norm.

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeNormalizerFitTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - columnsToNormalize
        - ColumnsToNormalize
        - Select the columns to normalize
      * - norm
        - Norm
        - 


Details
-------


 Sklearn Normalizer Node Details
+++++++++++++++

The Sklearn Normalizer Node is used to normalize samples individually to unit norm. It normalizes the input samples individually (in rows) to have unit norm, independently of the other samples. This can be useful for comparing samples with different scales.

It takes in the input data and normalizes the input samples individually to have unit norm. The input data can be in the form of a numpy array or a pandas DataFrame. It also takes two parameters: columnsToNormalize, which is the list of columns to normalize and norm, which is the norm to use to normalize the data. The norm can be "l2", "l1" or "max".

Input Parameters
```````````````

COLUMNS TO NORMALIZE : The list of columns to normalize.
NORM : The norm to use to normalize the data. It can be "l2", "l1" or "max".


Examples
-------


 Sklearn Normalizer Node Example
+++++++++++++++

Consider the below <b>Sklearn Normalizer</b> output for the <b>features</b> column

id features normalized_features
0 [1.0, 2.0, 3.0, 4.0] [0.1, 0.2, 0.3, 0.4]
1 [-1.0, -2.0, -3.0, -4.0] [-0.1, -0.2, -0.3, -0.4]
In this example, the input column is features and the output column is normalized_features. The columnsToNormalize parameter is set to features and the norm parameter is set to "l2". The normalizer normalizes the features column by dividing each value by the l2 norm of the column. Here the l2 norm is sqrt(1^2 + 2^2 + 3^2 + 4^2) = sqrt(30) = 5.477 so the features are divided by 5.477
