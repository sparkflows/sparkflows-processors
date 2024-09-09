Select Columns
=========== 

This node creates a new DataFrame that contains only the selected columns

Input
--------------
This type of node takes in a DataFrame and transforms it to another DataFrame.

Output
--------------
This node filters the specified columns from the incoming DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeColumnFilter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCols
        - Columns
        - Columns to be included in the output DataFrame


Details
-------


Select Columns Node Details
+++++++++++++++

This node creates a new DataFrame containing only the selected columns.

It selects columns that need to be passed to the outgoing Dataframe. 

Columns that need to be included in the outgoing Dataframe are to be selected in the 'Selected' list. Multiple columns can be selected in the list.


Examples
-------


Select Columns Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY
-------------------------------------------------------------------------------------
C01        |    MATT         |    50     |    12-02-2002         |    USD 200000.00
C02        |    LISA         |    45     |    15-11-2020         |    GBP 100000.00
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00
C04        |    MARCUS       |    35     |    01-01-2021         |    AUD 350000.00

Select Columns Node Configuration And Output
```````````````

[CUST_CD], [CUST_NAME] and [SALARY] columns from the incoming Dataframe are selected to be part of the outgoing Dataframe.
Outgoing Dataframe would be created as below containing only the selected columns:

CUST_CD    |    CUST_NAME    |    SALARY
-------------------------------------------------
C01        |    MATT         |    USD 200000.00
C02        |    LISA         |    GBP 100000.00
C03        |    ROBIN        |    EUR 15000.00
C04        |    MARCUS       |    AUD 350000.00
