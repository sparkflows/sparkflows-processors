Hive Incremental
=========== 

This node is used to incrementally read data from Hive table.

Output
--------------
It creates a DataFrame from selected hive table with latest data

Type
--------- 

dataset

Class
--------- 

fire.nodes.etl.NodeHiveIncremental

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - database
        - HIVE Database
        - HIVE Database
      * - table
        - HIVE Table
        - HIVE Table from which to read the data
      * - path
        - Watermark File Path
        - Path of the watermark file.
      * - filterFields
        - Incremental Load Fields
        - Comma separated values of field names used in data filter for the incremental load.
      * - outputColNames
        - Column Names of the database table
        - Column Names of the database table
      * - outputColTypes
        - Column Types of the database table
        - Column Types of the database table


Details
-------
Hive Incremental Node Details
---------------


This node reads a table from Hive and creates a DataFrame containing the schema and data of the specified table, with an incremental load configuration.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* HIVE DATABASE: Specify the Hive database from which data is to be read.
* HIVE TABLE: Specify the table in the Hive database from which data is to be read incrementally.
* WATERMARK FILE PATH: Define the file path for the watermark file to track the last load timestamp.
* INCREMENTAL LOAD FIELDS: Specify the fields that will be used for incremental loading (e.g., timestamp or ID fields).
* SCHEMA COLUMNS: Refresh the schema to load column names and types from the database table.


Examples
-------
Hive Incremental Node Examples
---------------



Example of Connection Values
+++++++++++++++


* OUTPUT STORAGE LEVEL: DEFAULT
* HIVE DATABASE: retail_db
* HIVE TABLE: sales_data
* WATERMARK FILE PATH: /user/hive/watermark/sales_data_watermark.txt
* INCREMENTAL LOAD FIELDS: sale_date
* SCHEMA COLUMNS: Click "Refresh Schema" to load columns from the specified Hive table.
