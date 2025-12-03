Recover Hive Partitions
=========== 

Node to recover the partitions of external hive table.

Type
--------- 

doc

Class
--------- 

fire.nodes.etl.NodeRecoverHivePartitions

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - databaseName
        - HIVE Database
        - Name of the HIVE Database
      * - tableName
        - HIVE Table
        - Name of the HIVE table


Details
===============
This node is used to recover the partitions of external hive table.


It will run the command: "MSCK REPAIR TABLE ${databaseName}.${tableName}"


