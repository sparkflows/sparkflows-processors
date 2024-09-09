Interaction
=========== 

This transformer takes in Double and Vector type columns and outputs a flattened vector of their feature interactions.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.etl.NodeInteraction

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Column containing label indices
      * - outputCol
        - Output Column
        - Output column name


Details
-------


 Interaction Node Details
+++++++++++++++

The Interaction Node is used to create a new column with feature interactions between the input columns. It takes in Double and Vector type columns and outputs a flattened vector of their feature interactions. It takes in a DataFrame and transforms it to another DataFrame by adding a new column with the feature interactions.
It takes in the parameters inputCols and outputCol, which are used for input column names and output column name respectively.

Input Parameters
```````````````

INPUT COLUMNS : Select the required columns for interaction.
OUTPUT COLUMN : The name of the output column after interaction.


Examples
-------


 Interaction Node Example
+++++++++++++++

Consider the below <b>Interaction</b> output for the <b>age</b> and <b>income</b> columns.

id age income Interaction
0  20  50000    [20,50000]
1  25  60000    [25,60000]
2  30  70000    [30,70000]

In this example, the input columns are age and income and the output column is Interaction. The interaction node creates a new column with the feature interactions between the input columns. The feature interactions in this case are the concatenation of the values in the columns age and income.
