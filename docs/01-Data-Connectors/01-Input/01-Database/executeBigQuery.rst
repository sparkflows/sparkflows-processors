Execute BigQuery
=========== 

It executes the query in BigQuery and creates a DataFrame from it

Input
--------------
It executes query.

Output
--------------
It creates a DataFrame from the executed query and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.gcp.NodeExecuteBigQuery

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
      * - query
        - Query
        - execute bigquery
      * - viewsEnabled
        - ViewsEnabled
        - 
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats
        - Format of the Output Columns
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Big Query.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
-------
It executes the query in BigQuery and creates a DataFrame from it

This node allows you to execute SQL queries directly against a BigQuery database. It provides a flexible way to interact with BigQuery and retrieve data for further processing.


Examples
-------
Execute BigQuery Node Example
---------------


Scenario:


Let's say you want to retrieve a list of customers from a BigQuery table named customers. You can use the following SQL query in the Execute BigQuery node:


SQL

SELECT customer_id, customer_name, customer_email

FROM customers;


Configuration:


Query: Enter the SQL query you want to execute.

Schema Columns: Optionally, you can specify the schema of the output DataFrame, including column names and data types.

Output:


The node will execute the query and return the results as a DataFrame. You can then use this DataFrame in subsequent nodes for further processing, such as filtering, transforming, or joining with other datasets.
