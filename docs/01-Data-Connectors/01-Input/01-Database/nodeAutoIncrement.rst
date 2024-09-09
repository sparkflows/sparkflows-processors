AutoIncrement
=========== 

This node reads data from Relational Databases using JDBC and creates a DataFrame from it

Input
--------------
It reads data from Relational Databases

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeAutoIncrement

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
      * - database
        - Database Name
        - 
      * - table
        - Table Name
        - 
      * - sqlkeycolumn
        - SQLKeyColumn
        - key column name
      * - sqlkeycolumntype
        - SQLKeyColumnType
        - index and timestamp type supported
      * - schema
        - Schema
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


This node reads data from Relational Databases using JDBC and creates a DataFrame from it.


