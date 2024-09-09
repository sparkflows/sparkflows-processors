Read From Snowflake
=========== 

This node reads a table from Snowflake

Output
--------------
Dataframe created from the data read from Snowflake

Type
--------- 

dataset

Class
--------- 

fire.nodes.snowflake.NodeReadFromSnowFlake

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - authType
        - Auth Type
        - Authentication Type. Possible value is OAUTH or USER_CREDENTIAL
      * - connection
        - Connection
        - The Snowflake connection to connect
      * - sfWarehouse
        - Snowflake Warehouse
        - Warehouse for connecting to the Snowflake
      * - sfDatabase
        - Snowflake Database
        - Database for connecting to the Snowflake
      * - sfSchema
        - Snowflake Schema
        - Schema for connecting to the Snowflake
      * - dbtable
        - Snowflake Table/View
        - Snowflake Table/View from which to read the data
      * - schema
        - Schema
      * - outputColNames
        - Output Column Names
        - Name of the Output Columns
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns


Details
-------


 Read from Snowflake Node Details
+++++++++++++++

This node reads a table from Snowflake and creates the DataFrame which contains the schema and data of the specified table.

 Parameters to be set:
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  CONNECTION : Select the desired snowflake connection to be used.
*  SNOWFLAKE WAREHOUSE : Specify the virtual warehouse to use for the connection.
*  SNOWFLAKE DATABASE : Specify the database to use once connected.
*  SNOWFLAKE SCHEMA : Specify the schema to use for the specified database once connected.
*  Snowflake TABLE/VIEW : Specify the table/view from which data is to be read.


Examples
-------


 Read From Snowflake Node Examples
+++++++++++++++

 Example of Connection Values
```````````````

*  CONNECTION : SNOWFLAKE_DEV_ENV_NCUS
*  SNOWFLAKE WAREHOUSE : SNOWFLAKE_BI_VWH
*  SNOWFLAKE DATABASE : CUSTOMER_SALES_NCUS
*  SNOWFLAKE SCHEMA : INT_NA_CUSTSALES
*  Snowflake TABLE/VIEW : CUST_BASIC
