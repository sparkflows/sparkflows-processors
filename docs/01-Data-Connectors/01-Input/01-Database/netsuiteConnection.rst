Read Netsuite
=========== 

This node reads data from Oracle Netsuite using token based authentication and creates a DataFrame from it

Input
--------------
It reads data from Oracle Netsuite

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.netsuite.NodeReadNetSuite

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - connection
        - Connection
        - The JDBC connection to connect
      * - tableName
        - Record Type
        - Filtering data based on record type
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Output Columns Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats


Details
-------
Read Netsuite Node Details
---------------


This node reads data from Netsuite and creates a DataFrame from it.



Parameters to be set:
+++++++++++++++

General:


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* CONNECTION: Select the desired JDBC connection to be used.
* DB TABLE: Specify the table from which data is to be read.

Schema:


* Schema Columns: Refresh the schema for loading column name,column type,column format.


