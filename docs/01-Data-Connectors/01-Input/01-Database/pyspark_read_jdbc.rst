Read JDBC
=========== 

This node writes data to databases using JDBC.

Type
--------- 

dataset

Class
--------- 

fire.nodes.save.NodeReadJDBC

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
      * - performance
        - Performance
        - 
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
      * - fetchsize
        - Fetch Size
        - The JDBC fetch size, which determines how many rows to fetch per round trip
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
      * - extraOptions
        - ExtraOptions
        - 
      * - extraOptionsKeys
        - Extra Options Keys
        - Extra options available for JDBC connections. Examples: connectTimeout --> Integer value in milliseconds. Sets the maximum time to wait for a connection to be established. socketTimeout --> Integer value in milliseconds. Specifies the timeout for socket reads. ssl --> 'true' or 'false'. Enables or disables SSL encryption for the connection. autoReconnect --> 'true' or 'false'. Automatically reconnects to the database if the connection fails. maxRows --> Integer value. Limits the number of rows returned by a query. useUnicode --> 'true' or 'false'. Defines whether to use Unicode character encoding for the connection. characterEncoding --> Specifies the character encoding to use for the connection, e.g., 'UTF-8'. allowMultiQueries --> 'true' or 'false'. Allows multiple SQL statements to be executed in a single query. retries --> Integer value. Number of connection retries in case of failure. useCursorFetch --> 'true' or 'false'. Enables cursor-based fetching for large result sets. rewriteBatchedStatements --> 'true' or 'false'. Optimizes batch processing by rewriting SQL statements for batch execution. fetchSize --> Integer value. Defines the number of rows to fetch in each database round trip. batchsize --> Integer value. Sets the batch size for batch inserts or updates.
      * - extraOptionsValues
        - Extra Options Values
        - Config Values for the Corresponding keys


Details
===============
Read JDBC Node Details
---------------


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


