Sklearn Binarizer Transform
=========== 

Binarize data (set feature values to 0 or 1) according to a threshold.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeBinarizerTransform

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


 Sklearn Binarizer Transform Node Details
+++++++++++++++

The Sklearn Binarizer Transform Node is used to binarize data (set feature values to 0 or 1) according to a threshold. It uses the sklearn library to apply the Binarizer transformation to the input data. This transformation can be useful for feature selection and preprocessing tasks.

Input Parameters
```````````````

THRESHOLD : The threshold value used to determine which feature values will be set to 1 and which will be set to 0.


Examples
-------


 Sklearn Binarizer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'values' containing numerical values. We use the Sklearn Binarizer Transform Node to binarize the 'values' column according to a threshold of 2.

Input DataFrame:

id values
1 [1.0,2.0,3.0,4.0]
2 [5.0,6.0,7.0,8.0]
3 [9.0,10.0,11.0,12.0]
4 [13.0,14.0,15.0,16.0]

Output

id values binarized_values
1 [1.0,2.0,3.0,4.0] [0,0,1,1]
2 [5.0,6.0,7.0,8.0] [1,1,1,1]
3 [9.0,10.0,11.0,12.0] [1,1,1,1]
4 [13.0,14.0,15.0,16.0] [1,1,1,1]

In this example, the input column is 'values' and the output column is 'binarized_values'. The Sklearn Binarizer Transform Node applies the Binarizer transformation to the 'values' column using a threshold of 2, creating a new column 'binarized_values' with the binarized feature values.
