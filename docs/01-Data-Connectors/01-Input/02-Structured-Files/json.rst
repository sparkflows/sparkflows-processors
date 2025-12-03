Read JSON
=========== 

Dataset Node for Reading JSON Files

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetJSON

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
        - Path of the JSON file/directory
      * - multiLine
        - Multi Line
        - 
      * - addInputFileName
        - Add Input File Name
        - Add the new field:input_file_name
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Name
        - New Output Column Name
      * - outputColTypes
        - Column Type
        - Data Type of the Output Column
      * - outputColFormats
        - Column Format
        - Format of the Output Column


Details
===============
Read JSON Node Details
---------------


This node reads a JSON file and creates the DataFrame which contains the schema and data of the specified JSON file.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the JSON file to be read.
* MULTI LINE : Select if the JSON file contains multi line JSON objects.
* ADD INPUT FILE NAME : Select if the JSON file name needs to be added to the DataFrame.
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.


Examples
===============
Read JSON Node Examples
---------------



Example of Values
+++++++++++++++


* PATH : /tmp/sample.json
* MULTI LINE : True
* ADD INPUT FILE NAME : True
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.
