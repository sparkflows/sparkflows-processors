Read Elastic Search
=========== 

Reads data from ElasticSearch

Type
--------- 

dataset

Class
--------- 

fire.nodes.elasticsearch.NodeReadElasticSearch

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - indexName
        - Index Name
        - Name of the Elastic Search Index
      * - elasticSearchHost
        - Elastic Search Host
        - Name of the Elastic Search Host
      * - elasticSearchPort
        - Elastic Search Port
        - Port of Elastic Search
      * - temporaryTable
        - Spark Temporary Table for Reading from ES
        - Spark Temporary Table to be used for reading from Elastic Search
      * - sql
        - SQL for reading from Elastic Search
        - SQL for reading from Elastic Search. Where condition can be applied here for limiting the rows read from ES.
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


This node reads data from ElasticSearch.


