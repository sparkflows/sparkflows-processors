Read JDBC
===========

This node reads data from Relational Databases using JDBC and creates a DataFrame from it

Input
--------------
It reads data from Relational Databases

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetJDBCUsingConnection

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
      * - jdbcDatabase
        - Database
        - Database for connecting to the JDBC
      * - jdbctable
        - Table
        - JDBC Table from which to read the data
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Output Columns Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats
      * - performance
        - Performance
        - 
      * - fetchsize
        - Fetch Size
        - The JDBC fetch size, which determines how many rows to fetch per round trip. This can help performance on JDBC drivers which default to low fetch size (e.g. Oracle with 10 rows).
      * - queryTimeout
        - Query Timeout
        - The number of seconds the driver will wait for a Statement object to execute. Zero means there is no limit.
      * - sessionInitStatement
        - Session Init Statement
        - After each database session is opened to the remote DB and before starting to read data, this parameter executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", "BEGIN execute immediate 'alter session set "_serial_direct_read"=true'; END;").
      * - partitionColumn
        - Partition Column
        - PartitionColumn must be a numeric, date, or timestamp column from the table
      * - lowerBound
        - Lower Bound
        - LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - upperBound
        - Upper Bound
        - LowerBound and UpperBound are just used to decide the partition stride, not for filtering the rows in the table. All rows in the table will be partitioned and returned. This option applies only to reading
      * - numPartitions
        - Num Partitions
        - The maximum number of partitions that can be used for parallelism in table reading
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Read JDBC.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
-------
Read JDBC Node Details
+++++++++++++++


This node reads data from Relational Databases using JDBC and creates a DataFrame from it.



Parameters to be set:
+++++++++++++++

General:


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* CONNECTION: Select the desired JDBC connection to be used.
* DB TABLE: Specify the table from which data is to be read.

Performance:


* PARTITION COLUMN: The column used to partition the table data for parallel reads.
* LOWER BOUND: The minimum value for the partition column to start data partitioning.
* UPPER BOUND: The maximum value for the partition column to end data partitioning.
* NUM PARTITIONS: Number of partitions for parallel data processing.
* FETCH SIZE: Number of rows to fetch per call; helps optimize data retrieval performance.

Schema:


* Schema Columns: Refresh the schema for loading column name,column type,column format.


