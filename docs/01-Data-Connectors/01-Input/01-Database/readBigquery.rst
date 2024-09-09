Read BigQuery
=========== 

It reads data from BigQuery table and creates a DataFrame from it

Input
--------------
It reads data from BigQuery table.

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.gcp.NodeReadBigQuery

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - bigQueryDataset
        - BigQuery Dataset
        - bigQueryDataset name
      * - bigQueryTable
        - BigQuery Table
        - BigQueryTable name.
      * - outputColNames
        - Column Names
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats
        - Format of the Output Columns




