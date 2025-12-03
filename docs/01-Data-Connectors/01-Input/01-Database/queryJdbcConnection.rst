Query JDBC
=========== 

This node executes query on Relational Databases using JDBC and creates a DataFrame from it

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

fire.nodes.dataset.NodeJDBCQueryUsingConnection

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
      * - query
        - Query
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
      * - pushDownPredicate
        - Push Down Predicate
        - Enable or disable predicate push-down into the JDBC data source. The default value is true, in which case Spark will push down filters to the JDBC data source as much as possible.
      * - pushDownAggregate
        - Push Down Aggregate
        - Enable or disable aggregate push-down in V2 JDBC data source. The default value is false, in which case Spark will not push down aggregates to the JDBC data source. Aggregate push-down is usually turned off when the aggregate is performed faster by Spark than by the JDBC data source. Please note that aggregates can be pushed down if and only if all the aggregate functions and the related filters can be pushed down.
      * - fetchsize
        - Fetch Size
        - The JDBC fetch size, which determines how many rows to fetch per round trip. This can help performance on JDBC drivers which default to low fetch size (e.g. Oracle with 10 rows).
      * - queryTimeout
        - Query Timeout
        - The number of seconds the driver will wait for a Statement object to execute. Zero means there is no limit.
      * - sessionInitStatement
        - Session Init Statement
        - After each database session is opened to the remote DB and before starting to read data, this parameter executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", "BEGIN execute immediate 'alter session set "_serial_direct_read"=true'; END;").
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


Details
-------
Query JDBC Node Details
---------------


This node executes query on Relational Databases using JDBC and creates a DataFrame from it.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* CONNECTION : Select the desired connection to be used.
* QUERY : Specify the SQL query to execute to retrieve data from the database.
* SCHEMA COLUMNS : Refresh the schema for loading column name,column type,column format.


Examples
-------
Query JDBC Node Examples
---------------



Example of Connection Values
+++++++++++++++


* CONNECTION : JDBC_Connection
* QUERY : SELECT * FROM customers WHERE country = 'USA'
* SCHEMA COLUMNS : Refresh the schema for loading column name,column type,column format.
