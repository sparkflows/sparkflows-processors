Standard Scaler
=========== 

StandardScaler transforms a dataset of Vector rows, normalizing each feature to have unit standard deviation and/or zero mean.

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
It adds a new column containing the transform of the input Vector column to unit standard deviation and/or zero mean features to the incoming DataFrame.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeStandardScaler

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
      * - withMean
        - With Mean
        - Centers the data with mean before scaling.
      * - withStd
        - With Standard Dev
        - Scales the data to unit standard deviation


Details
-------


 Standard Scaler Node Details
+++++++++++++++

The Standard Scaler Node is used to normalize a dataset of Vector rows, by transforming each feature to have unit standard deviation and/or zero mean. It takes in the common parameters inputCol, outputCol, withMean, and withStd. The input column should be in the format of VectorUDT. The output column will also be in the format of VectorUDT.

The inputCol is the name of the feature column to be transformed. The outputCol is the name of the new column containing the transformed features. The withMean parameter, when set to true, centers the data with mean before scaling. The withStd parameter, when set to true, scales the data to unit standard deviation.

Input Parameters
```````````````

INPUT COLUMN : Select the required column for which Standard scaling has to be done .
OUTPUT COLUMN : The name of the output column after standard scaling.
WITH MEAN : Centers the data with mean before scaling.
WITH STANDARD DEVIATION : Scales the data to unit standard deviation.


Examples
-------


 Standard Scaler Node Example
+++++++++++++++

Consider the below <b>Standard Scaler</b> output for the <b>features</b> column

id features scaled_features
0 [1.0, 2.0, 3.0, 4.0] [-1.3416407864998738, -0.4472135954999579, 0.4472135954999579, 1.3416407864998738]
1 [-1.0, -2.0, -3.0, -4.0] [1.3416407864998738, 0.4472135954999579, -0.4472135954999579, -1.3416407864998738]
In this example, the input column is features and the output column is scaled_features. The standard scaler scales the features to unit standard deviation by subtracting the mean of the features and then dividing by the standard deviation. The withMean parameter is set to true and withStd parameter is set to true. Here the mean of the features is (1.0+2.0+3.0+4.0)/4 = 2.5 and the standard deviation is sqrt((1^2+2^2+3^2+4^2)/4-2.5^2) = 1.2909944487358056.
