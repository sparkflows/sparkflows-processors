Read Iceberg
===========

It reads data from Iceberg table and creates a DataFrame from it

Input
--------------
It reads data from Iceberg table.

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.iceberg.ReadIcebergTable

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
        - Warehouse path for Hive or Hadoop catalog, Hadoop Catalog path is required and For Hive Catalog it's optional(by default warehouse path is used.).
      * - databaseName
        - HIVE Database
        - HIVE Database
      * - tableName
        - HIVE Table
        - HIVE Table from which to read the data
      * - icebergDatabaseName
        - Iceberg Database
        - Iceberg Database
      * - icebergTableName
        - Iceberg Table
        - Iceberg Table from which to read the data
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




