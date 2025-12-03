Update JDBC
=========== 

This node update the data to selected columns.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeUpdateJDBC

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - primaryKeyColumn
        - Primary Key Column
        - Key column name in table
      * - updateColumn
        - Update Column
        - Update column name in table
      * - table
        - DB Table
        - The JDBC table to write to
      * - connection
        - Connection
        - The JDBC connection to connect


Details
-------
Update JDBC Node Details
---------------


This node update the data to selected columns.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* PRIMARY KEY COLUMN: Specify the column(s) that uniquely identify rows in the database table, Select the primary key column(s) from the "Available" list and move them to the "Selected" list.
* UPDATE COLUMN: Specify the column(s) that you want to update in the database table, Select the columns to be updated from the "Available" list and move them to the "Selected" list.
* DB TABLE: Specify the name of the database table where data will be updated.
* CONNECTION: Select the desired database connection to use.


Examples
-------
Update JDBC Node Examples
---------------



Example of Updating Columns
+++++++++++++++


* PRIMARY KEY COLUMN: customer_id
* UPDATE COLUMN: (email_address,last_login_date),This configuration would update the email_address and last_login_date for records in the database table, matching rows based on their customer_id.
* DB TABLE:  customers
* CONNECTION:  MY_POSTGRES_DB, This configuration would update the email_address and last_login_date for records in the customers table using the MY_POSTGRES_DB connection.
