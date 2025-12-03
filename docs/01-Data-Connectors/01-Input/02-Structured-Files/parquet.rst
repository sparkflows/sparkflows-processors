Read Parquet
=========== 

Dataset Node for reading Apache Parquet Files

Input
--------------
It reads in Parquet files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetParquet

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
        - Path of the Parquet file/directory
      * - addInputFileName
        - Add Input File Name
        - Add the new field:input_file_name
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names for the Parquet
        - Output Columns of the Parquet
      * - outputColTypes
        - Column Types for the Parquet
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Parquet
        - Format of the Output Columns


Details
-------
Read Parquet Node Details
---------------


This node reads a Parquet file and creates the DataFrame which contains the schema and data of the specified Parquet file.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the Parquet file to be read.
* ADD INPUT FILE NAME : Select if the Parquet file name needs to be added to the DataFrame.
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.


Examples
-------
Read Parquet Node Examples
---------------



Example of Values
+++++++++++++++


* PATH : /tmp/sample.parquet
* ADD INPUT FILE NAME : False
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.
