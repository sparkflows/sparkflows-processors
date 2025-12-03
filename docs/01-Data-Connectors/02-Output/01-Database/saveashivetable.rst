Save As HIVE Table
=========== 

Saves the DataFrame into an Apache HIVE Table

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveAsTable

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
        - Name of the HIVE Database
      * - table
        - HIVE Table
        - Name of the HIVE table
      * - format
        - Format
        - File format when saving to HIVE Table
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
        - 
      * - partitionBy
        - Partition By
        - List of columns to partition by - separated by space
      * - numBuckets
        - NumBuckets
        - Number of buckets
      * - bucketBy
        - Bucket By
        - List of columns to bucket by - separated by space


Details
-------
Save As HIVE Table Node Details
---------------


Saves the DataFrame into an Apache HIVE Table.



Parameters to be set:
+++++++++++++++

General:


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* HIVE DATABASE: Specify the HIVE database where the table will be created.
* HIVE TABLE: Specify the name of the HIVE table to which the data will be written.
* FORMAT: Choose the file format for the HIVE table (e.g., Parquet, ORC, CSV, Json).
* SAVE MODE: Choose how to save data in the table, if any (Append, Overwrite, ErrorIfExists, Ignore).

Advanced:


* PARTITION BY: (Optional) Specify columns to partition the HIVE table. You can select multiple columns from the "Available" list and move them to the "Selected" list to define the partitioning schema.
* NUM BUCKETS: Specify the number of buckets to use when bucketing the HIVE table.
* BUCKET BY: (Optional) Specify columns to bucket the HIVE table. You can select multiple columns from the "Available" list and move them to the "Selected" list to define the bucketing scheme.


Examples
-------
Save As HIVE Table Node Examples
---------------



Example of Connection Values
+++++++++++++++

General:


* HIVE DATABASE: my_hive_db
* HIVE TABLE: processed_customer_data
* FORMAT: Parquet
* SAVE MODE: Overwrite

Advanced:


* PARTITION BY: (year,month,country), This would create a partitioned HIVE table where data is organized into directories based on year, month, and country.
* NUM BUCKETS:  32
* BUCKET BY:  customer_id, This would create a bucketed HIVE table where data is divided into 32 buckets based on the customer_id column.
