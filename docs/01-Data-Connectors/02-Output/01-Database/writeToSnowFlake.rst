Write To Snowflake
=========== 



Input
--------------
The Dataframe from the previous node

Output
--------------
The incoming Dataframe is passed to the next node as it is

Type
--------- 

transform

Class
--------- 

fire.nodes.snowflake.NodeWriteToSnowFlake

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
        - Snowflake Table
        - Snowflake Table from which to write the data
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the table Exists


Details
-------


 Write To Snowflake Node Details
+++++++++++++++

This node saves the rows of the incoming dataframe into the specified table in Snowflake.

 Parameters to be set:
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  CONNECTION : Select the desired snowflake connection to be used.
*  SNOWFLAKE WAREHOUSE : Specify the virtual warehouse to use for the connection.
*  SNOWFLAKE DATABASE : Specify the database to use once connected.
*  SNOWFLAKE SCHEMA : Specify the schema to use for the specified database once connected.
*  SNOWFLAKE TABLE : Specify the table from which data is to be read.
*  SAVE MODE : Select the mode of operation on the table. 

Append: If data/table already exists, contents of the table are to be appended to existing data. 
Overwrite: If table already exists, existing data is overwritten by the new content. 
ErrorIfExists: If data already exists, an exception is thrown and operation stops.
Ignore: If table already exists, the save operation is ignored.


Examples
-------


 Write To Snowflake Node Examples
+++++++++++++++

 The below example will save the input dataframe to the `CUST_BASIC_LA` table.
```````````````


*  CONNECTION : SNOWFLAKE_DEV_ENV_NCUS
*  SNOWFLAKE WAREHOUSE : SNOWFLAKE_BI_VWH
*  SNOWFLAKE DATABASE : CUSTOMER_SALES_NCUS
*  SNOWFLAKE SCHEMA : INT_NA_CUSTSALES
*  SNOWFLAKE TABLE : CUST_BASIC_LA
*  SAVE MODE : Overwrite
