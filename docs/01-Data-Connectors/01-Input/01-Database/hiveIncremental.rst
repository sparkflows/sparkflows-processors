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




