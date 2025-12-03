Save JDBC
=========== 

This node writes data to databases using JDBC.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveJDBC1

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
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Save JDBC.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
===============
Save JDBC Node Details
---------------


This node writes data to databases using JDBC.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Keep this as DEFAULT.
* CONNECTION: Select the desired database connection to use.
* DB TABLE: Specify the name of the database table where the data will be written.
* TRUNCATE: Choose whether to truncate (delete all existing data from) the table before writing (true or false).
* SAVE MODE: Choose how to save existing data in the table (Append, Overwrite, ErrorIfExists, Ignore).

-Append: If data/table already exists, contents of the table are to be appended to existing data. 

-Overwrite: If table already exists, existing data is overwritten by the new content. 

-ErrorIfExists: If data already exists, an exception is thrown and operation stops.

-Ignore: If table already exists, the save operation is ignored.


Examples
===============
Save JDBC Node Examples
---------------



Example of Connection Values
+++++++++++++++


* OUTPUT STORAGE LEVEL: DEFAULT
* CONNECTION: MY_POSTGRES_DB
* DB TABLE: customer_data
* TRUNCATE: false
* SAVE MODE: Append
