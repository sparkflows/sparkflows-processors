Generate UUID
=========== 

This node Generates a Universally Unique ID

Input
--------------
It accepts a dataframe as input

Output
--------------
It adds a new column for UUID to the input DataFrame. This new DataFrame is sent to the output

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeGenerateUUID

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCol
        - Output Column
        - Output Column Name


Details
-------


Generate UUID Node Details
+++++++++++++++

This node Generates a Universally Unique ID for each row. Generated UUID value is added as a column to the outgoing Dataframe.

Input
```````````````

*    OUTPUT COLUMN :- Enter name of the column to list the generated UUID values in the outgoing Dataframe.


Output
```````````````

*    New output column would be added to the Outgoing Dataframe listing the generated UUID values for each row.


Examples
-------


Generate UUID Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

DATA_COLS
-------------------------------------------
CUST001INV00120200101PRD0011200
CUST001INV00220200202PRD0022200

Generate UUID node Configuration and Output
```````````````

GenerateUUID node is configured to generate UUID for each row and add it as a new column [UUID_VAL]. 
Outgoing Dataframe would be created as below with new column [UUID_VAL] added to it:

DATA_COLS                           |    UUID_VALUE
------------------------------------------------------------------------------------
CUST001INV00120200101PRD0011200     |    61e55caa-22c6-4648-a26d-98df31f11784
CUST001INV00220200202PRD0022200     |    c70b2c9d-773a-45c2-acd7-bd3d256a4419
