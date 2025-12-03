ReadFlatFile
=========== 

Creates a dataset with output schema from schema field with values extracted from fixedlength.

Input
--------------
It does not read data from any external source

Output
--------------
It creates a DataFrame with columns from schema field.

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeReadFlatFile

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputDataPath
        - Input Data Path
        - Path of the file/directory
      * - schemaPath
        - SchemaPath
        - Schema File Path with schema:fieldname,datatype,defaultValue,startindex,endindex. When filetype is fixed-length then startindex & endindex columns will be used.
      * - fileType
        - File Type
        - different type of flat files
      * - addInputFileName
        - Add Input File Name
        - Add the new field:input_file_name
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names
        - Output Columns
      * - outputColTypes
        - Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats
        - Format of the Output Columns




