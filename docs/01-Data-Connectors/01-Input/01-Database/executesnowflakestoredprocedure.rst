Execute Stored Procedure In Snowflake
===========

This node executes Stored Procedure in Snowflake

Output
--------------
Pass the return data from SP to in next node and pass the input dataframe to next node.

Type
--------- 

shellcommand

Class
--------- 

fire.nodes.snowflake.NodeExecuteStoredProcedureInSnowFlake

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
        - Authentication Type. Possible value is OAUTH or USER_CREDENTIAL or KEYPAIR
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
      * - extraOptionsKeys
        - JDBC Properties Name
        - Extra JDBC Properties Name.
      * - extraOptionsValues
        - JDBC Properties Value
        - Extra JDBC Properties Value
      * - storedProcedureInputConfiguration
        - StoredProcedureInputConfiguration
        - 
      * - storedProcedureStmt
        - Stored Procedure Stmt
        - example: call return_value_proc(?)
      * - parameterType
        - SP Parameter Type
        - Stored Procedure input parameter Type: string, integer, double, float, boolean and datetime.
      * - parameterValue
        - SP Parameter Value
        - Stored Procedure input parameter values.
      * - storedProcedureOutputConfiguration
        - StoredProcedureOutputConfiguration
        - 
      * - returnValueName
        - SP Return Value Name
        - Stored Procedure ouput Return Value Name.
      * - returnValueType
        - SP Return Type
        - Stored Procedure ouput Return Value Type: string, integer, double, float, boolean and datetime..




Examples
-------
Execute Query In Snowflake Node Examples
+++++++++++++++



Example of Connection Values
+++++++++++++++


* CONNECTION : SNOWFLAKE_DEV_ENV_NCUS
* SNOWFLAKE WAREHOUSE : SNOWFLAKE_BI_VWH
* SNOWFLAKE DATABASE : CUSTOMER_SALES_NCUS
* SNOWFLAKE SCHEMA : INT_NA_CUSTSALES
* Stored Procedure Stmt :call return_value_proc(?)
