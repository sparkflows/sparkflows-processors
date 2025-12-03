InMemoryDataset
===========

Dataset Node for createing the in-memory dataframe from passed data and fieldstr

Input
--------------
Create the in-memory dataframe

Output
--------------
It creates a DataFrame from the dataSte and fieldStr

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetInMemory

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - dataType
        - Data Type
        - Data type
      * - dataStr
        - Data Str
        - Check the example tab for more details
      * - fieldDefsStr
        - Field Defs Str
        - Enter the Field Defs Str, name:type. example:id:Integer,name:String,score:Float,signup_date:Date
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names for the fieldstr
        - Output Columns of the Delta
      * - outputColTypes
        - Column Types for the Delta
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Delta
        - Format of the Output Columns


Details
-------
Read InMemoryDataset Node Details
+++++++++++++++


Dataset Node for creating the InMemoryDataset.


Examples
-------
InMemoryDataset Node Examples
+++++++++++++++



Example of Field Values
+++++++++++++++

Data Type: json

Data Str : [

{"id":1,"name":"Alice","score":85.5},

{"id":2,"name":"Bob","score":92.3}

]


Data Type: comma_delimited

Data Str : 1,John,75.5,2023-05-01,true,2023-05-01T12:34:56

2,Alice,80.0,2024-01-15,false,2024-01-15 08:00:00

Field Defs Str: id:Integer,name:String,score:Float,signup_date:Date,active:Boolean,logged_at:Timestamp
