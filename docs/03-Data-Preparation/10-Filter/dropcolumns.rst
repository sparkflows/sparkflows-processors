Drop Columns
=========== 

This node creates a new DataFrame by dropping the specified columns

Input
--------------
It takes in a DataFrame as input

Output
--------------
The specified columns are dropped from the incoming DataFrame to generate the output DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDropColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - dropCols
        - Columns
        - The columns to be excluded from the output DataFrame


Details
-------


Drop Columns Node Details
+++++++++++++++

This node creates a new DataFrame by dropping the selected columns.

It drops the selected columns from the outgoing dataframe. 

Columns that need to be dropped are to be selected in the 'Selected' list. Multiple columns can be selected in the list that needs to be dropped.


Examples
-------


Drop Columns Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe having following columns:


*  CUST_CD
*  CUST_NAME
*  DOB
*  ADDRESS


Drop Columns Node Configuration And Output
```````````````

[DOB] and [ADDRESS] columns are selected to be dropped from the outgoing Dataframe. 
Outgoing dataframe would contain only below two columns after dropping the selected columns:


*  DOB
*  ADDRESS
