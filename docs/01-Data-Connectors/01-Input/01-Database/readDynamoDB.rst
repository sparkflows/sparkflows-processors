Read DynamoDB
=========== 

This node reads data from DynamoDB and gets the credentials from the instance profile.

Type
--------- 

dataset

Class
--------- 

fire.nodes.dynamodb.NodeReadDynamoDB

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
        - DynamoDB Table from which to read the data.
      * - roleArn
        - RoleArn
        - RoleArn used to access the table.
      * - region
        - Region
        - AWS Region
      * - outputColNames
        - Column Names
        - Column Names
      * - outputColTypes
        - Column Types
        - Data Types
      * - outputColFormats
        - Column Formats
        - Formats


Details
-------


This node reads data from DynamoDB.


