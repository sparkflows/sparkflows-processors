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
      * - table
        - DB Table
        - The JDBC table to write to
      * - truncate
        - Truncate
        - Whether to truncate the table in case Save Mode is Overwrite
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the table Exists




