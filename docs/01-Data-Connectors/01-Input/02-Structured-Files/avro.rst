Read Avro
=========== 

Dataset Node for Reading Apache Avro Files

Input
--------------
It reads in Avro Files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetAvro

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
        - Path of the Avro file/directory
      * - addInputFileName
        - Add Input File Name
        - Add the new field:input_file_name
      * - outputColNames
        - Column Names for the Avro
        - Output Columns of the Avro
      * - outputColTypes
        - Column Types for the Avro
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Avro
        - Format of the Output Columns


Details
-------


This node reads data from Apache Avro files.


