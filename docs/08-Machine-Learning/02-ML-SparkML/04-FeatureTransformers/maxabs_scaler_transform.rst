MaxAbs Scaler Transform
=========== 

Rescale each feature individually to range [-1, 1] by dividing through the largest maximum absolute value in each feature.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodeMaxAbsScalerTransform

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


 MaxAbs Scaler Transform Node Details
+++++++++++++++

The MaxAbs Scaler Transform Node is used to apply the MaxAbs scaler transformation on a given dataset. It takes in a fit MaxAbs scaler model as input, which has been trained on a dataset, and applies the same scaling on the input dataset. It is used for transforming new data after a model has been fit.
It takes in no input parameters as it requires a fit MaxAbs scaler model as input to perform the transformation.


