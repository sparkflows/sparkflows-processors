Join Using SQL
=========== 

This node registers the incoming DataFrames as temporary tables and executes the SQL provided

Input
--------------
It takes in 2 or more DataFrames as input and produces one DataFrame as output by executing the provided SQL.

Output
--------------
The DataFrame created as a result of executing the join SQL

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeJoinUsingSQL

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - tempTables
        - Temp Table Names
        - Temp Table Name to be used
      * - sql
        - SQL
        - SQL to be run
      * - schema
        - Schema
      * - outputColNames
        - Column Names for the CSV
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types for the CSV
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the CSV
        - Format of the Output Columns


Details
-------


Join Using SQL Details
+++++++++++++++


*  This node receives two or more input data frames and creates the corresponding temporary tables.
*  Allows the user to write a SQL query to join these temporary tables.
*  The resulting output dataframe contains the output of the SQL execution.


Examples
-------


Join Using SQL Examples
+++++++++++++++

 Two-table joins
```````````````

The following example shows a two-table join:
SELECT order_num, lname, fname FROM tempTable1, tempTable2
WHERE tempTable1.customer_num = tempTable2.customer_num

 Multi-table joins
```````````````

The following multiple-table join yields the company name of the customer who ordered an item as well as its stock number and manufacturer code:
SELECT DISTINCT company, stock_num, manu_code
FROM tempTable1 c, tempTable2 o, tempTable3 i
WHERE c.customer_num = o.customer_num
AND o.order_num = i.order_num;

 LEFT OUTER joins
```````````````

The below table join yields data of all customers irrespective of whether or not they have placed any orders:
SELECT c.ID, c.NAME, o.AMOUNT, o.DATE
FROM tempTable1 c
LEFT OUTER JOIN tempTable2 o
ON (c.ID = o.CUSTOMER_ID)
