Sklearn Binarizer
=========== 

Binarize data (set feature values to 0 or 1) according to a threshold.

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeBinarizerFitTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - threshold
        - Threshold
        - 


Details
-------


 Sklearn Binarizer Node Details
+++++++++++++++

The Sklearn Binarizer Node is used to binarize data, meaning it sets feature values to 0 or 1 according to a threshold. The threshold parameter is the value above which the features will be set to 1 and below which the features will be set to 0. It is a scalar value.

It takes in the input data and applies the threshold to the feature values. The input data can be in the form of a numpy array or a pandas DataFrame.

Input Parameters
```````````````

THRESHOLD : A scalar value above which the feature values will be set to 1 and below which the feature values will be set to 0.


Examples
-------


 Sklearn Binarizer Node Example
+++++++++++++++

Consider the below <b>Sklearn Binarizer</b> output for the <b>features</b> column

id features binarized_features
0 [1.0, 2.0, 3.0, 4.0] [0, 0, 0, 1]
1 [-1.0, -2.0, -3.0, -4.0] [0, 0, 0, 0]
In this example, the input column is features and the output column is binarized_features. The threshold is set to 0.0. The feature values above threshold are set to 1 and below threshold are set to 0. In this example all feature values are greater than 0.0 so the binarized_features column will have all 1's.
