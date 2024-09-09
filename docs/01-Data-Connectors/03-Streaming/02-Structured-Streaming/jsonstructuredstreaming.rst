Structured Streaming JSON
=========== 

It monitors a specified directory for new files. It keeps reading in any new files created in the directory.

Input
--------------
It does not take any DataFrame as input

Output
--------------
It reads the new files and creates DataFrame from the content of the text files. This DataFrame is passed to the output Nodes.

Type
--------- 

sparkstreaming

Class
--------- 

fire.nodes.structuredstreaming.NodeStructuredStreamingJSON

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
        - Path of the Text file/directory
      * - outputColNames
        - Column Names for the JSON
        - Output Column Names
      * - outputColTypes
        - Column Types for the JSON
        - Output Column Types
      * - outputColFormats
        - Column Formats for the JSON
        - Output Column Formats




