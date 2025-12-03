DB Incremental Ingestion
=========== 

This node incrementally fetches data from a database table based on a key column (DATE, ID, or TIMESTAMP). It handles both initial and subsequent data.

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

fire.nodes.dataset.NodeDBIncrementalIngestion

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
      * - maxIncrementSize
        - Max Increment Size
        - For date, specify the number of days. For index, specify the number of records. For timestamp, specific the number of hours.
      * - startValue
        - Start Value
        - use start value instead of minimum value for first run
      * - keycolumnName
        - Key Column Name
        - key column name
      * - keycolumntype
        - Key Column Type
        - index, timestamp or date type supported
      * - keycolumnformat
        - Key Column Format
        - timestamp column format
      * - performance
        - Performance
        - 
      * - partitionColumn
        - Partition Column
        - PartitionColumn must be a numeric, date, or timestamp column from the table
      * - numPartitions
        - Num Partitions
        - The maximum number of partitions that can be used for parallelism in table reading
      * - fetchsize
        - Fetch Size
        - The JDBC fetch size, which determines how many rows to fetch per round trip
      * - sessionInitStatement
        - Session Init Statement
        - After each database session is opened to the remote DB and before starting to read data, this parameter executes a custom SQL statement (or a PL/SQL block). Use this to implement session initialization code. Example: option("sessionInitStatement", "BEGIN execute immediate 'alter session set "_serial_direct_read"=true'; END;").
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


Details
-------
This node incrementally fetches data from a database table based on a key column (DATE, ID, or TIMESTAMP). It handles both initial and subsequent data.


