Interaction Transform
=========== 

This transformer takes in Double and Vector type columns and outputs a flattened vector of their feature interactions.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.etl.NodeInteractionTransform

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


 Interaction Transform Node Details
+++++++++++++++

The Interaction Transform Node is used to create a new vector column which is the flattened vector of the feature interactions between two or more input columns. It takes in Double and Vector type columns and outputs a flattened vector of their feature interactions.
It also takes in a fit model as input, which is typically the output of a previous Interaction Estimator Node.

Input Parameters
```````````````

FIT MODEL : The output of a previous Interaction Estimator Node, which contains the information about the columns to be interacted.


Examples
-------


 Interaction Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with columns 'age' and 'income' of type Double and 'features' of type Vector. We use a Interaction Estimator Node to specify the columns to be interacted, creating a fit model. Then, we use the Interaction Transform Node to transform the columns using the fit model.

Input DataFrame:

id age income features
1 22 30000 [1.0, 2.0, 3.0, 4.0]
2 35 50000 [-1.0, -2.0, -3.0, -4.0]

Output DataFrame

id age income features interaction
1 22 30000 [1.0, 2.0, 3.0, 4.0] [0.44, 0.88, 1.32, 1.76, 660000, 1100000, 1540000, 1980000]
2 35 50000 [-1.0, -2.0, -3.0, -4.0] [-0.44, -0.88, -1.32, -1.76, -175000, -350000, -525000, -700000]
In this example, the input columns are 'age', 'income' and 'features' and the output column is 'interaction'. The fit model is created using the Interaction Estimator Node. The Interaction Transform Node uses this fit model to create a new column 'interaction' which is the flattened vector of the feature interactions between 'age', 'income' and 'features'.
