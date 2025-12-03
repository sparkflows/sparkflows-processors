Save JDBC
=========== 

This node writes data to databases using JDBC.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveJDBC

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
      * - jdbcDatabase
        - Database
        - Database for connecting to the JDBC
      * - jdbctable
        - Table
        - JDBC Table from which to read the data
      * - truncate
        - Truncate
        - Whether to truncate the table in case Save Mode is Overwrite
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the table Exists
      * - extraOptions
        - Extra Options
        - 
      * - extraOptionsKeys
        - Extra Options Keys
        - Extra options available for JDBC connections
      * - extraOptionsValues
        - Extra Options Values
        - Config Values for the Corresponding keys


Details
-------
Save JDBC Node Details
---------------


This node writes data to databases using JDBC.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* CONNECTION: Select the desired database connection to use.
* DB TABLE: Specify the name of the database table where data will be written.
* TRUNCATE: Choose whether to truncate (delete all existing data from) the table before writing (true or false).
* SAVE MODE: Choose how to handle existing data in the table (Append, Overwrite, ErrorIfExists, Ignore).


Examples
-------
Save JDBC Node Examples
---------------



Example of Connection Values
+++++++++++++++


* CONNECTION: MY_POSTGRES_DB
* DB TABLE: customer_data
* TRUNCATE: false
* SAVE MODE: Append
