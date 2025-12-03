JDBC Incremental Load
=========== 

This node is used to load incremental data from RDBMS to Hive.

Input
--------------
RDBMS detail like URL, Username , Password, Hive DB , Hive Table name

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetJDBCIncrementalLoad

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
      * - sqltable
        - SQL Table
        - 
      * - sqlkeycolumn
        - SQL Key Column
        - 
      * - sqlkeycolumntype
        - SQL Key Column type
        - 
      * - homeDirectory
        - Config Path
        - 
      * - performance
        - Performance
        - 
      * - partitionColumn
        - Partition Column
        - PartitionColumn must be a numeric, date, or timestamp column from the table
      * - lowerBound
        - LowerBound
        - LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - upperBound
        - UpperBound
        - LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - numPartitions
        - NumPartitions
        - The maximum number of partitions that can be used for parallelism in table reading
      * - fetchsize
        - FetchSize
        - The JDBC fetch size, which determines how many rows to fetch per round trip
      * - schema
        - InferSchema
        - 
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
JDBC Incremental Load Node Details
---------------


This node is used to load incremental data from RDBMS to Hive.



Parameters to be set:
+++++++++++++++

General:


* OUTPUT STORAGE LEVEL: Define the data storage level, DEFAULT is typically used for standard storage.
* CONNECTION: Select the JDBC connection to the target database.
* SQL TABLE: Enter the name of the table from which incremental data is to be loaded.
* SQL KEY COLUMN: Specify the unique key column used to track incremental changes.
* SQL KEY COLUMN TYPE: Indicate the data type of the key column (e.g.,INTEGER,VARCHAR).
* CONFIG PATH: Path to any additional configuration files needed for the connection.

Performance:


* PARTITION COLUMN: Choose a column to split the data into partitions for parallel data loading.
* LOWERBOUND: Set the minimum value for the partition column to define the start of data partitioning.
* UPPERBOUND: Set the maximum value for the partition column to define the end of data partitioning.
* NUMPARTITIONS: Specify the number of partitions to enable parallel data processing.
* FETCHSIZE: Define the number of rows fetched per call to optimize retrieval performance.

Schema:


* SCHEMA COLUMNS: Use the Refresh Schema option to update the schema, which loads the column names, data types, and formats of the selected SQL table.


