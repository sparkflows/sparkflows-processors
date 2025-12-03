Read HIVE Table
===========

This node reads data from Apache HIVE table and creates a DataFrame from it

Input
--------------
It reads in CSV text files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.hive.NodeHIVE

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - db
        - HIVE Database
        - HIVE Database
      * - table
        - HIVE Table
        - HIVE Table from which to read the data
      * - query
        - HIVE Query (Optional)
        - If a separate HIVE query needs to be used for reading from HIVE. This field is optional.
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Database table
        - Column Names of the Database table
      * - outputColTypes
        - Column Types of the Database table
        - Column Types of the Database table


Details
-------
Read HIVE Table Node Details
+++++++++++++++


This node reads data from the Apache HIVE table and creates a DataFrame from it.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* HIVE DATABASE: Specify the HIVE database to use.
* HIVE TABLE: Specify the table within the HIVE database to read.
* HIVE QUERY (OPTIONAL): (If needed) Provide a custom SQL query to retrieve data from the HIVE table.


Examples
-------
Read HIVE Table Node Examples
+++++++++++++++



Example of Connection Values
+++++++++++++++


* HIVE DATABASE: my_hive_db
* HIVE TABLE: customer_transactions
* HIVE QUERY (OPTIONAL): SELECT customer_id, SUM(transaction_amount) FROM customer_transactions GROUP BY customer_id
