Save Delta
=========== 

Saves the DataFrame into the specified location in Delta Format.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveDelta

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - path
        - Path
        - Path to save the delta files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names
      * - mergeSchema
        - Merge Schema
        - If true, then any columns that are present in the DataFrame but not in the target table are automatically added on to the end of the schema as part of a write transaction
      * - overwriteSchema
        - Overwrite Schema
        - If true, overwrites the schema of the Delta table with the schema of the incoming DataFrame
      * - optimizeWrite
        - Optimize Write
        - If true, it optimizes Spark partition sizes based on the actual data
      * - overwritePartitionPredicate
        - Overwrite Partition Predicate
        - If specified, then it selectively overwrites only the data that satisfies the given where clause expression.
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in read delta.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
===============
Save Delta Node Details
---------------


This node Saves the DataFrame into the specified location in Delta Format.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Choose how the data should be stored (e.g., DEFAULT, DISK_ONLY).
* PATH: Specify the directory where the Delta Lake table will be saved. Use the "Browse" button to navigate and select the desired location.
* SAVE MODE: Choose how to save existing data in the table (Append, Overwrite, ErrorIfExists, Ignore).

Append: If data/table already exists, contents of the table are to be appended to existing data. 

Overwrite: If table already exists, existing data is overwritten by the new content. 

ErrorIfExists: If data already exists, an exception is thrown and operation stops.

Ignore: If table already exists, the save operation is ignored.


Examples
===============
Save Delta Node Examples
---------------



Example of Saving Data to Delta Lake
+++++++++++++++


* OUTPUT STORAGE LEVEL: DEFAULT
* PATH: /user/hive/warehouse/my_delta_table
* SAVE MODE: Overwrite
