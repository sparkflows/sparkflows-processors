AutoIncrement
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

fire.nodes.dataset.NodeAutoIncrement

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
      * - database
        - Database Name
        - 
      * - table
        - Table Name
        - 
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
      * - properties
        - Properties
        - 
      * - keycolumnName
        - Key Column Name
        - key column name
      * - keycolumntype
        - Key Column Type
        - index, timestamp or date type supported
      * - keycolumnformat
        - Key Column Format
        - timestamp column format
      * - onSchemaChange
        - On Schema Change
        - IgnoreSchemaChanges: Don’t check or react to schema changes., FailOnSchemaChange:Abort execution if schema has changed.,AutoHandleSchemaChanges:Automatically handle schema changes (e.g., add/remove columns as needed).
      * - performance
        - Performance
        - 
      * - filter
        - filter
        - filter condition to select the required rows.
      * - partitionColumn
        - Partition Column Name
        - PartitionColumn must be a numeric, date, or timestamp column from the table
      * - partitionColType
        - Partition Column Type
        - index, timestamp or date type supported
      * - numPartitions
        - Num Partitions
        - The maximum number of partitions that can be used for parallelism in table reading
      * - fetchsize
        - Fetch Size
        - The JDBC fetch size, which determines how many rows to fetch per round trip. This can help performance on JDBC drivers which default to low fetch size (e.g. Oracle with 10 rows).
      * - pushDownPredicate
        - Push Down Predicate
        - Enable or disable predicate push-down into the JDBC data source. The default value is true, in which case Spark will push down filters to the JDBC data source as much as possible.
      * - pushDownAggregate
        - Push Down Aggregate
        - Enable or disable aggregate push-down in V2 JDBC data source. The default value is false, in which case Spark will not push down aggregates to the JDBC data source. Aggregate push-down is usually turned off when the aggregate is performed faster by Spark than by the JDBC data source. Please note that aggregates can be pushed down if and only if all the aggregate functions and the related filters can be pushed down.
      * - queryTimeout
        - Query Timeout
        - The number of seconds the driver will wait for a Statement object to execute. Zero means there is no limit.
      * - sessionInitStatement
        - Session Init Statement
        - After each database session is opened to the remote DB and before starting to read data, this parameter executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", "BEGIN execute immediate 'alter session set "_serial_direct_read"=true'; END;").


Details
-------
This node reads data from Relational Databases using JDBC and creates a DataFrame from it.


