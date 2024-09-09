Read Databricks Table
=========== 

This node reads a table from Databricks

Input
--------------
It reads data from the Databricks Table

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.databricks.NodeReadDatabricksTable

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - db
        - Databricks Database
        - Databricks Database
      * - table
        - Databricks Table
        - Databricks Table from which to read the data
      * - query
        - Databricks Query (Optional)
        - If a separate Databricks query needs to be used for reading from the Databricks table, This field is optional.
      * - schema
        - Schema
      * - outputColNames
        - Column Names of the Table
        - Output Column Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats


Details
-------


 Read Databricks Table Node Details
+++++++++++++++

This node reads a table in Databricks and creates the DataFrame which contains the schema and data of the specified table.

 Parameters to be set:
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  DATABRICKS DATABASE : Specify the database to use.
*  DATABRICKS TABLE : Specify the table from which data is to be read.
*  DATABRICKS QUERY (OPTIONAL) : Specify the full query that is to be executed.


Examples
-------


 Read Databricks Table Node Examples
+++++++++++++++

 The below example will retrieve all records from the `EMP` table residing inside the `EMPLOYEEDB` database. 
```````````````

*  DATABRICKS DATABASE : EMPLOYEEDB
*  DATABRICKS TABLE : EMP


 The below example includes the `DATABRICKS QUERY` parameter. This will return all the records from `EMP` table, displaying only two columns.
```````````````

*  DATABRICKS DATABASE : EMPLOYEEDB
*  DATABRICKS TABLE : EMP
*  DATABRICKS QUERY : Select first_name, last_name from EMP
