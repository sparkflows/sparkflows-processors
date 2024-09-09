Execute Query In Snowflake
=========== 

This node executes query in Snowflake

Output
--------------
Dataframe created from the data read in from Snowflake

Type
--------- 

dataset

Class
--------- 

fire.nodes.snowflake.NodeExecuteQueryInSnowFlake

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
      * - query
        - Snowflake Query
        - 
      * - outputColNames
        - Output Column Names
        - Name of the Output Columns
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns




Examples
-------


 Execute Query In Snowflake Node Examples
+++++++++++++++

 Example of Connection Values
```````````````

*  CONNECTION : SNOWFLAKE_DEV_ENV_NCUS
*  SNOWFLAKE WAREHOUSE : SNOWFLAKE_BI_VWH
*  SNOWFLAKE DATABASE : CUSTOMER_SALES_NCUS
*  SNOWFLAKE SCHEMA : INT_NA_CUSTSALES
*  SNOWFLAKE QUERY : SELECT FIRST_NAME, LAST_NAME, DATEADD('DAY',90,START_DATE) FROM EMP_BASIC WHERE START_DATE <= '2017-01-01'


 Another example of a query using multiple tables would be 
```````````````
SELECT EMPLOYEES.TITLE,EMPLOYEES.EMPLOYEE_ID,MANAGERS.EMPLOYEE_ID AS MANAGER_ID, MANAGERS.TITLE AS "MANAGER TITLE"
FROM EMPLOYEES, MANAGERS
WHERE EMPLOYEES.MANAGER_ID = MANAGERS.EMPLOYEE_ID
ORDER BY EMPLOYEES.TITLE
