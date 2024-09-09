Min Max Scaler
=========== 

MinMaxScaler transforms a dataset of Vector rows, rescaling each feature to a specific range (often [0, 1])

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
A new column containing the scaled features is added to the incoming DataFrame

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeMinMaxScaler

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
      * - max
        - Max
        - The upper bound after transformation, shared by all features
      * - min
        - Min
        - The lower bound after transformation, shared by all features


Details
-------


Min Max Scaler Node Details
+++++++++++++++

The Min Max Scaler node transforms a dataset of Vector rows, rescaling each feature to a specific range (often [0, 1]). MinMaxScaler computes summary statistics on a data set and produces a MinMaxScalerModel. The model can then transform each feature individually such that it is in the given range.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : A vector value where the columns to be rescaled have been converted into a single vector column
*  OUTPUT COLUMN : A transformed version of the dataset with each column normalized independently
*  MAX : 1.0 by default. Upper bound after transformation, shared by all features.
*  MIN : 0.0 by default. Lower bound after transformation, shared by all features.


Examples
-------


Min Max Scaler Node Example
+++++++++++++++

Consider the below raw dataset showing 2 columns with 4 rows:
[[100, 0.001],
 [8, 0.05],
 [50, 0.005],
 [88, 0.07],
 [4, 0.1]]

- We will first create a single feature vector using the <b>VectorAssembler</b> node that will combine the given list of columns into a single vector column.
- Next we will use the generated vector column as the input column for the <b>MinMaxScaler</b> node.
- Keeping the <b>Min</b> and <b>Max</b> value as default, this node will transforms data by scaling features to the given range. It scales the values to a specific value range without changing the shape of the original distribution.
