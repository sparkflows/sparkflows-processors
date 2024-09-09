Imputer
=========== 

Imputation estimator for completing missing values

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeImputer

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
        - Column containing inputs
      * - outputCol
        - Output Column
        - Output column names
      * - strategy
        - Strategy
        - Imputer strategy


Details
-------


 Imputer Node Details
+++++++++++++++

The Imputer Node is used to complete missing values in a dataset. It takes in a DataFrame and transforms it to another DataFrame by filling the missing values in the input columns.
It takes in the parameters inputCols, outputCols and strategy, which are used for input column names, output column names and the imputation strategy respectively.

Input Parameters
```````````````

INPUT COLUMNS : Select the required columns for imputation.
OUTPUT COLUMNS : The name of the output columns after imputation.
STRATEGY : The imputation strategy can be mean, median or mode.


Examples
-------


 Imputer Node Example
+++++++++++++++

Consider the below <b>Imputer</b> output for the <b>age</b> and <b>income</b> columns with strategy mean.

id age income
0  20   50000
1 null  60000
2 30    null

The imputed Dataframe will be

id age income
0   20 50000
1   25 60000
2   30 58333.3333

In this example, the input columns are age and income and the output columns are also age and income. The imputer fills the missing values in the input columns with the mean of the column. Here the mean of age column is 25 and mean of income column is 58333.3333
