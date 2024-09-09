Sklearn Normalizer Transform
=========== 

Normalize samples individually to unit norm.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeNormalizerFitTransformSklearn

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


 Sklearn Normalizer Transform Node Details
+++++++++++++++

The Sklearn Normalizer Transform Node is used to normalize the samples of a DataFrame individually to unit norm. It uses the sklearn library to apply the Normalizer transformation to the input data. This transformation can be useful for feature scaling and normalization tasks. The Normalizer scales the features by transforming them such that the sum of their squares is equal to 1.

Input Parameters
```````````````

NORM : The norm to use to normalize the samples. Default is 'l2'


