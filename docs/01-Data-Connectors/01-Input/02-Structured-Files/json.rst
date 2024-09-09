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
-------


It reads JSON files. Each JSON record has to be on a separate line for Spark to handle it correctly.

There cannot be a line break within a record.


