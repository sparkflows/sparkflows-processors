Binarizer
=========== 

Binarize a column of continuous features given a threshold.

Input
--------------
This type of node takes in a DataFrame and transforms it to another DataFrame

Output
--------------
A new column containing the binarized values is added to the incoming DataFrame

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeBinarizer

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
      * - threshold
        - Threshold
        - The features greater than the threshold, will be binarized to 1.0.The features equal to or less than the threshold, will be binarized to 0.0.


Details
-------


 Binarizer Node Details
+++++++++++++++

The Binarizer Node is used in the process of thresholding numerical features to binary (0/1) features.

Binarizer takes the common parameters inputCol and outputCol, as well as the threshold for binarization. 
Feature values greater than the threshold are binarized to 1.0; values equal to or less than the threshold are binarized to 0.0. 
Both Vector and Double types are supported for inputCol.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the required column for whom binarization has to be done . 
*  OUTPUT COLUMN : The name of the output binarized column.
*  THRESHOLD : Set the threshold used to binarize continuous features. The features greater than the threshold, will be binarized to 1.0. The features equal to or less than the threshold, will be binarized to 0.0. Default: 0.0


Examples
-------


 Binarization Node Example
+++++++++++++++

Consider the below <b>Binarizer</b> output for the <b>feature</b> column with <b>Threshold</b> set to 0.5
-------------------------------
| id|feature|binarized_feature|
-------------------------------
|  0|    0.1|              0.0|
|  1|    0.8|              1.0|
|  2|    0.2|              0.0|
-------------------------------
