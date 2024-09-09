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




