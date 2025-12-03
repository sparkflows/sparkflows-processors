Write To BigQuery
=========== 



Input
--------------
The Dataframe from the previous node

Output
--------------
The incoming Dataframe is passed to the next node as it is

Type
--------- 

transform

Class
--------- 

fire.nodes.gcp.NodeSaveBigQuery

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - connection
        - Connection
        - The JDBC connection to connect
      * - bigQueryDataset
        - BigQuery Dataset
        - bigQueryDataset name
      * - bigQueryTable
        - BigQuery Table
        - BigQueryTable name.
      * - temporaryBucket
        - Temporary Bucket
        - Temporary bucket to store while transferring data.
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the table Exists
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Save Big Query.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name




