Register TempTable
=========== 

This node registers the incoming DataFrame as a temporary table in Spark

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
The incoming DataFrame is output without any changes

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRegisterTempTable

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - tempTable
        - Temporary Table
        - Name of the temporary table to be created


Details
===============
Register Temp Table Node
---------------


This node registers the incoming DataFrame as a temporary table in the Spark SQL context. This allows you to query the DataFrame using SQL queries.


Examples
===============
Register Temp Table Node Example
---------------


Given the following dataset:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

B2    S2    Nut    Hardware    7

C3    S3    Screw    Hardware    9


After registering this DataFrame as a temporary table named temp_table, you can query it using SQL like this:


SQL

SELECT * FROM temp_table WHERE PartQualityScore > 7;

Use code with caution.


This query would return the following result:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

C3    S3    Screw    Hardware    9
