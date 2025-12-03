Execute CRUD Stmt In Snowflake
===========

This node executes Stored Procedure in Snowflake

Output
--------------
pass the input dataframe to next node.

Type
--------- 

shellcommand

Class
--------- 

fire.nodes.snowflake.NodeExecuteCURDStmtInSnowflake

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
      * - curdStmtConfiguration
        - CRUD Stmt Configuration
        - 
      * - curdStmt
        - CRUD Stmt
        - CRETE, DROP, INSERT, UPDATE AND DELETE
      * - inputType
        - CRUD Input Type
        - CRUD Input Type: string, integer, double, float, boolean and datetime.
      * - inputValue
        - CRUD Input Value
        - CRUD Input Value.




