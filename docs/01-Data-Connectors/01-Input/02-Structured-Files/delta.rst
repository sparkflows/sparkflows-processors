Read Delta
=========== 

Dataset Node for reading Apache Delta files

Input
--------------
It reads in Delta files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetDelta

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
        - Path of the Delta file/directory
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names for the Delta
        - Output Columns of the Delta
      * - outputColTypes
        - Column Types for the Delta
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Delta
        - Format of the Output Columns
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Read Delta.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
===============
Read Delta Node Details
---------------


Dataset Node for reading Apache Delta files.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the delta file.
* SCHEMA COLUMNS: Refresh the schema for loading column name,column type,column format.


Examples
===============
Read Delta Node Examples
---------------



Example of Connection Values
+++++++++++++++


* PATH : Specify the path of the delta file.
* SCHEMA COLUMNS: Refresh the schema for loading column name,column type,column format.
