SQL Executer
=========== 

This node runs the given SQL query

Input
--------------
This type of node takes the sql query of any statement type

Output
--------------
This node executes the given SQL query

Type
--------- 

dataset

Class
--------- 

fire.nodes.runrdbmssql.NodeSqlExecuter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - url
        - Db Url
        - URL of SQL
      * - driver
        - driver class name
        - driver class name for SQL
      * - user name
        - User Name
        - User name of SQL
      * - password
        - password
        - password of SQL
      * - statementType
        - Statement Type
        - statementType of SQL
      * - query
        - query
        - query to execute


Details
===============
SQL Executor Node
---------------


This node executes a specified SQL query against a database. The results of the query are returned as a DataFrame.


Examples
===============
SQL Executor Node Example
---------------


Given a database table named customers with the following schema:


Column Name    Data Type

customer_id    INT

customer_name    STRING

customer_email    STRING


To retrieve all customers with the email domain example.com, you can use the following SQL query in the SQL Executor node:


SQL

SELECT * FROM customers WHERE customer_email LIKE '%@example.com';


The output of this query would be a DataFrame containing the selected customer information.
