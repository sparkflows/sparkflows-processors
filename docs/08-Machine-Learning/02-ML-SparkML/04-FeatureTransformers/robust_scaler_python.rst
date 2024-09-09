Robust Scaler
=========== 

RobustScaler removes the median and scales the data according to the quantile range

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeRobustScaler

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
        - Column containing input
      * - outputCol
        - Output Column
        - Output column names
      * - withCentering
        - withCentering
        - Output column names
      * - withScaling
        - withCentering
        - Output column names


Details
-------


 Robust Scaler Node Details
+++++++++++++++

The Robust Scaler Node is used to scale a dataset individually feature-wise according to the quantile range. It removes the median and scales the data according to the quantile range.
It takes in the common parameters inputCol and outputCol, which are the input and output column names. The input column should be in the format of VectorUDT. Additionally it takes in withCentering and withScaling parameters which are used to center and scale the data respectively.

Input Parameters
```````````````

INPUT COLUMN : Select the required column for which scaling has to be done .
OUTPUT COLUMN : The name of the output column after scaling.
WITH CENTERING : A Boolean parameter which indicates whether to center the data before scaling.
WITH SCALING : A Boolean parameter which indicates whether to scale the data.


Examples
-------


 Robust Scaler Node Example
+++++++++++++++

Consider the below <b>Robust Scaler</b> output for the <b>features</b> column

id features scaled_features
0 [1.0, 2.0, 3.0, 4.0] [-0.5, 0.0, 0.5, 1.0]
1 [-1.0, -2.0, -3.0, -4.0] [-1.0, -0.5, 0.0, 0.5]

In this example, the input column is features and the output column is scaled_features. The robust scaler removes the median and scales the data according to the quantile range. The withCentering is set to true, so the data is centered before scaling and withScaling is set to true, so the data is scaled.
