Read Redshift-AWS
=========== 

This node reads data from Redshift using JDBC.

Type
--------- 

dataset

Class
--------- 

fire.nodes.aws.NodeReadRedshift

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - url
        - URL
        - The JDBC URL to connect to
      * - dbtable
        - Redshift Table
        - The Redshift table that should be read. Note that anything that is valid in a FROM clause of a SQL query can be used. For example, instead of a full table you could also use a subquery in parentheses.
      * - awsAccessKeyId
        - AWS Access Key Id
        - AWS Access Key Id
      * - awsSecretAccessKey
        - AWS Secret Access Key
        - AWS Secret Access Key
      * - tempS3Dir
        - Temporary S3 directory
        - Temporary S3 directory
      * - outputColNames
        - Column Names of the Table
        - Output Columns Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats


Details
-------


This node reads data from Redshift using JDBC.


