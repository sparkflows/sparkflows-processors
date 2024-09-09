Filter Unique
=========== 

This node splits the incoming DataFrame into two output DataFrames one having unique values and other having rest of duplicates

Input
--------------
It accepts a DataFrame as input from the previous Node

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeUnique

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Filter By Columns
        - Columns to be used for filtering


Details
-------


Filter Unique Details
+++++++++++++++
This Node Separates data into two streams, unique and duplicate rows, based on the columns you choose.
Filter unique filters out unique data from the dataset based on input columns and outputs it in lower edge.
It outputs rest of the values (duplicates which were dropped) in the higher edge.


Examples
-------


Incoming Dataframe has following rows:
```````````````

CUST_CD   |   CUST_NAME    |   AGE
------------------------------------
C01       |   MATT         |   50
C02       |   DAVID        |   45
C03       |   DAVID        |   35
C04       |   DAVID        |   30

If Filter Unique node is configured as:
         Filter By Columns: CUST_NAME
then two outgoing Dataframes would be created as below:

First Dataframe with only Unique Values
```````````````

CUST_CD   |   CUST_NAME    |   AGE
------------------------------------
C01       |   MATT         |   50
C02       |   DAVID        |   45

Second Dataframe with all duplicate values except for the one that got output in above dataframe
```````````````

CUST_CD   |   CUST_NAME   |   AGE
------------------------------------
C03       |   DAVID       |   35
C04       |   DAVID       |   30
