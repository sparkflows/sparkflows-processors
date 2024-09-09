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
      * - outputColNames
        - Column Names for the Parquet
        - Output Columns of the Parquet
      * - outputColTypes
        - Column Types for the Parquet
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Parquet
        - Format of the Output Columns




