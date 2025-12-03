Parse JSON Col
=========== 

Parses JSON content in a given column

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeParseJSONColumn

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - jsonColName
        - JSON Col Name
        - Specifies the input column containing the JSON data
      * - inputCol
        - Input Col
        - Input Columns
      * - jsonFieldNames
        - JSON Field names
        - JSON Field names
      * - jsonFieldTypes
        - JSON Field Type
        - Data Type of the JSON field
      * - advance
        - Advance
        - 
      * - stringJsonColNames
        - String Json ColNames
        - Specifies the input column containing the JSON data
      * - outputJsonColNames
        - Output ColNames
        - uses the schema from the column you provide and create the new output column.
      * - outputSchema
        - InferSchema
        - 
      * - outputColNames
        - Output Column Name
        - Output Columns
      * - outputColTypes
        - Output Column Type
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Format
        - Format of the Output Columns


Details
===============
Parse JSON Column Node
---------------



Overview:
+++++++++++++++


The Parse JSON Column node parses a JSON column into individual columns. It's useful for extracting specific fields from JSON data.



Input:
+++++++++++++++


JSON Column Name: The name of the column containing the JSON data.

Variables: A table to define the JSON fields to extract and their corresponding data types.


Output:
+++++++++++++++


The node creates new columns for each specified JSON field, extracting the relevant data from the JSON column.


Examples
===============
Example:


Let's assume we have a column named json_data containing JSON data like this:


JSON

{

  "name": "John Doe",

  "age": 30,

  "city": "New York"

}


Configure the Node:


JSON Column Name: json_data

Variables:

Input Col: json_data

JSON Field Name: name

JSON Field Type: string

Input Col: json_data

JSON Field Name: age

JSON Field Type: integer

Input Col: json_data

JSON Field Name: city

JSON Field Type: string

Node Execution:


The node will create three new columns: name, age, and city, extracting the corresponding values from the json_data column.
