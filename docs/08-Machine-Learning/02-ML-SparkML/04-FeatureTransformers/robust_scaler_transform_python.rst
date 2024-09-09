Robust Scaler Transform
=========== 

RobustScaler removes the median and scales the data according to the quantile range

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeRobustScalerTransform

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


 Robust Scaler Transform Node Details
+++++++++++++++

The Robust Scaler Transform Node is used to remove the median and scales the data according to the quantile range. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous Robust Scaler Estimator Node.
The transformed DataFrame contains a new column with the scaled data according to the quantile range.

Input Parameters
```````````````

FIT MODEL : The output of a previous Robust Scaler Estimator Node, which contains the information about the quantile range for the scaling.


Examples
-------


 Robust Scaler Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'income' containing continuous values. We use a Robust Scaler Estimator Node to specify the quantile range for the scaling, creating a fit model. Then, we use the Robust Scaler Transform Node to scale the 'income' column using the fit model.

Input DataFrame:

id income
1 50000
2 75000
3 100000
4 125000

Output

id income income_scaled
1 50000 -1.0
2 75000 -0.5
3 100000 0.0
4 125000 0.5
In this example, the input column is 'income' and the output column is 'income_scaled'. The fit model is created using the Robust Scaler Estimator Node. The Robust Scaler Transform Node uses this fit model to scale the 'income' column, creating a new column 'income_scaled' with the scaled data.
