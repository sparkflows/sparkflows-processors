Save DynamoDB
=========== 

Saves the rows of the incoming DataFrame into DynamoDB and get the credentials from the instance profile.

Type
--------- 

transform

Class
--------- 

fire.nodes.dynamodb.NodeSaveDynamoDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - table
        - DynamoDB Table
        - Write to table by overwriting existing item with same keys
      * - writeBatchSize
        - WriteBatchSize
        - number of items to send per call to DynamoDB BatchWriteItem. Default 25.
      * - targetCapacity
        - TargetCapacity
        - fraction of provisioned write capacity on the table to consume for writing or updating. Default 1 (i.e. 100% capacity).
      * - update
        - Update
        - if true items will be written using UpdateItem on keys rather than BatchWriteItem. Default false.
      * - throughput
        - Throughput
        - the desired write throughput to use. It overwrites any calculation used by the package. It is intended to be used with tables that are on-demand. Defaults to 100 for on-demand.


Details
-------


This node saves the rows of the incoming DataFrame into Dynamo DB.


