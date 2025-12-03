Read XML
===========

It reads in XML files and creates a DataFrame from it

Input
--------------
It reads in XML Text Files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetXML

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
      * - rowTag
        - Row Tag
        - Row Tag
      * - addInputFileName
        - Add Input File Name
        - Add the new field:input_file_name
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names for the CSV
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types for the CSV
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the CSV
        - Format of the Output Columns


Details
-------
Read XML Node Details
+++++++++++++++


This node reads an XML file and creates the DataFrame which contains the schema and data of the specified XML file.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the XML file to be read.
* ROW TAG : Specify the tag which is to be considered as a row.
* ADD INPUT FILE NAME : Select if the XML file name needs to be added to the DataFrame.
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.


Examples
-------
Read XML Node Examples
+++++++++++++++



Example of Values
+++++++++++++++


* PATH : /tmp/sample.xml
* ROW TAG : item
* ADD INPUT FILE NAME : False
* SCHEMA COLUMNS : Refresh the schema of the DataFrame.
