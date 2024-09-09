Drop Null Rows for Selected Columns
=========== 

This node creates a new DataFrame by dropping rows containing null values for selected Columns

Input
--------------
It accepts DataFrame as input from the previous Node

Output
--------------
This node drops rows containing null values for selected Columns

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDropRowsWithNullMultipleColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - columns_to_check
        - Columns to Check
        - Columns to be processed for missing values


Details
-------


This node creates a new DataFrame by dropping rows containing NULL values in selected columns.


Examples
-------


Incoming Dataframe has following rows:

EMP_CD    |    EMP_NAME    |    DEPT       |    AGE
-------------------------------------------------------
E01       |    DAVID       |    HR         |    25
E05       |    MARK        |               |    25
E02       |    JOHN        |    SALES      |    35
E03       |    TONY        |    MARKETING  |    
E04       |    MARTIN      |    MARKETING  |    45

Incoming Dataframe has NULL values for two rows. For selected Columns DEPT and AGE,
using DropRowsWithNull node would result in below outgoing Dataframe created by dropping rows having NULL values for selected columns:

EMP_CD    |    EMP_NAME    |    DEPT       |    AGE
-------------------------------------------------------
E01       |    DAVID       |    HR         |    25
E02       |    JOHN        |    SALES      |    35
E04       |    MARTIN      |    MARKETING  |    45
