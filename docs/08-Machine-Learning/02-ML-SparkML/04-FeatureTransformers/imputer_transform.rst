Imputer Transform
=========== 

Imputation estimator for completing missing values

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodeImputerTransform

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


 Imputer Transform Node Details
+++++++++++++++

The Imputer Transform Node is used to impute missing values in a dataset. It takes in a fit model as input, which is typically the output of a previous Imputer Estimator Node, and uses it to fill in missing values in a DataFrame.

Input Parameters
```````````````

FIT MODEL : The output of a previous Imputer Estimator Node, which contains the imputation strategy and parameters used for filling in missing values.


Examples
-------


 Imputer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with columns 'age' and 'income' containing missing values. We use an Imputer Estimator Node to specify the imputation strategy as 'mean' and create a fit model. Then, we use the Imputer Transform Node to fill in the missing values in the 'age' and 'income' columns using the fit model.

Input DataFrame

id	age	income
1	22	null
2	null	35
3	45	45
4	55	null
Imputer Estimator Node
Imputation strategy = 'mean'

Imputer Transform Node
Input = DataFrame, Fit Model
Output =

id	age	income
1	22	40
2	40	35
3	45	45
4	55	40
In this example, the input DataFrame contains missing values in the 'age' and 'income' columns. The fit model is created using the Imputer Estimator Node with the imputation strategy set to 'mean'. The Imputer Transform Node uses this fit model to fill in the missing values.
