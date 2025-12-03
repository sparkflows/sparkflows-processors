Save Parquet
=========== 

Saves the DataFrame into the specified location in Parquet Format. When running on Hadoop, it is saved onto HDFS.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveParquet

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
        - Path where to save the Parquet files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names
      * - createDataset
        - Auto create dataset
        - Select Models
      * - datasetName
        - Dataset Name
        - Dataset Name


Details
-------
Save Parquet Node Details
---------------


Saves the DataFrame into the specified location in Parquet Format. When running on Hadoop, it is saved onto HDFS.



Parameters to be set:
+++++++++++++++

General:


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the Parquet file to be saved.
* SAVE MODE : Specify the save mode - Append, Overwrite, ErrorIfExists and Ignore.

Advanced:


* PARTITION COLUMN NAMES : Specify the columns to be used for partitioning the Parquet files.


Examples
-------
Save Parquet Node Examples
---------------



Example of Values
+++++++++++++++

General:


* PATH : /tmp/sample.parquet
* SAVE MODE : Append

Advanced:


* PARTITION COLUMN NAMES : col1,col2
