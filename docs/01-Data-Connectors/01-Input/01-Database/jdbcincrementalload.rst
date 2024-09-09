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
      * - partitionColumn
        - Partition Column
        - PartitionColumn must be a numeric, date, or timestamp column from the table
      * - lowerBound
        - LowerBound
        -  LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - upperBound
        - UpperBound
        -  LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - numPartitions
        - NumPartitions
        - The maximum number of partitions that can be used for parallelism in table reading
      * - fetchsize
        - FetchSize
        - The JDBC fetch size, which determines how many rows to fetch per round trip
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


This node is used to load incremental data from RDBMS to Hive.


