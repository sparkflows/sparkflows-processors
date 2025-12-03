Save Iceberg
=========== 



Input
--------------
The Dataframe from the previous node

Output
--------------
The incoming Dataframe is passed to the next node as it is

Type
--------- 

transform

Class
--------- 

fire.nodes.iceberg.WriteIcebergTable

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - catalogName
        - Iceberg Catalog
        - Catalog name
      * - catalogType
        - Catalog Type
        - Choose Catalog type - hadoop or hive
      * - metastoreUri
        - Hive metastore uri
        - Hive metastore uri
      * - warehousePath
        - Warehouse path
        - Warehouse path for Hadoop and Hive catalog
      * - databaseName
        - HIVE Database
        - HIVE Database
      * - tableName
        - HIVE Table
        - HIVE Table from which to save the data
      * - icebergDatabaseName
        - Iceberg Database
        - Iceberg Database
      * - icebergTableName
        - Iceberg Table
        - Iceberg Table from which to save the data
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the table Exists
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names




