Add Column Advanced
=========== 

This node allows adding new columns with certain values

Input
--------------
This type of node takes in a DataFrame and transforms it to another DataFrame

Output
--------------
This node adds the user specified columns to the DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeAddConstantColumn

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - constantTypes
        - Constant Type
        - Constant Types
      * - outputCols
        - Output Column
        - New Output column name.
      * - constantValues
        - Constant Value
        - ConstantValues when type is ConstantString and ConstantInt.


Details
-------


It creates a new DataFrame by adding new columns to the input Dataframe.

New columns can be created for selected types from dropdown in `Constant Types` field.

In Output Columns field provide the name of new columns.

In Constant Values field provide the respective constant value when type is ConstantString or ConstantInt.

When type is CurrentDate or CurrentTimeStamp, leave the Constant Values field should be left empty - currentdate and currentimestamp values will be get populated automatically.

This node supports the multiple add columns - Multiple constant type columns can be added.


Examples
-------


If option for adding new columns is selected as below with new column names specified in bracket


*  CurrentDate (Column Name CurrentDate)
*  CurrentTimeStamp (Column Name CurrentTimeStamp)
*  STRING Column with a value DrillMachine (Column Name MACHINE_NAME)
*  INTEGER column with a value 100 (Column Name MACHINE_WEIGHT)


then following columns would be added to the output Dataframe with mentioned values:


*  CURRENT_DATE : 2021-10-22
*  CURRENT_TIME : 2021-10-22 04:34:00.532
*  MACHINE_NAME : DrillMachine
*  MACHINE_WEIGHT : 100
