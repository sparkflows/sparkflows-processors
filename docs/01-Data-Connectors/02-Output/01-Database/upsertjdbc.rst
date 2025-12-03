Upsert JDBC
=========== 

This node insert or update the data to databases using JDBC.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeUpsertJDBC

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - primaryKeyColumn
        - PrimaryKeyColumn
        - Key column name in table
      * - table
        - DB Table
        - The JDBC table to write to
      * - connection
        - Connection
        - The JDBC connection to connect


Details
===============
Upsert JDBC Node Details
---------------


This node updates or inserts (upserts) data in a database table using JDBC. It allows you to synchronize data between your DataFrame and the database table.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* PRIMARY KEY COLUMN: Specify the column(s) that uniquely identify rows in the database table. You need to select the primary key column(s) from the "Available" list and move them to the "Selected" list using the arrow buttons.
* DB TABLE: Specify the name of the database table to be updated or inserted into.
* CONNECTION: Select the desired database connection to use.


Examples
===============
Upsert JDBC Node Examples
---------------



Example of Upserting Data
+++++++++++++++


* PRIMARY KEY COLUMN: product_id
* DB TABLE: products
* CONNECTION: MY_SQL_DB

This configuration would upsert data into the products table using the MY_SQL_DB connection, The product_id column is used to match rows between the DataFrame and the database table, If a row with a matching product_id exists in the table, it will be updated, otherwise, a new row will be inserted.
