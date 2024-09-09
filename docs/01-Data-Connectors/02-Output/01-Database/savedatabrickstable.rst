Save Databricks Table
=========== 

This node saves a input data as table in Databricks

Input
--------------
It take dataframe as input data.

Output
--------------
It creates a Table in Databricks from the dataframe(input data).

Type
--------- 

transform

Class
--------- 

fire.nodes.databricks.NodeSaveDatabricksTable

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - database
        - Databricks Database
        - Name of the Database
      * - table
        - Databricks Table
        - Name of the table
      * - format
        - Format
        - File format when saving to Table
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
      * - partitionBy
        - Partition By
        - List of columns to partition by - separated by ,


Details
-------


 Save Databricks Table Node Details
+++++++++++++++

This node reads the input dataframe and then saves the schema and data as a Databricks table.

 Parameters to be set:
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  DATABRICKS DATABASE : Specify the database to use.
*  DATABRICKS TABLE : Specify the table to be created or reused.
*  FORMAT : Optional, By default data gets saved in parquet format.
*  SAVE MODE : Select the mode of operation on the table. 

Append: If data/table already exists, contents of the table are to be appended to existing data. 
Overwrite: If table already exists, existing data is overwritten by the new content. 
ErrorIfExists: If data already exists, an exception is thrown and operation stops.
Ignore: If table already exists, the save operation is ignored.
  


Examples
-------


 Save Databricks Table Node Examples
+++++++++++++++

 The below example will save the input dataframe to the `EMP` table.
```````````````
 * DATABRICKS DATABASE : EMPLOYEEDB

*  DATABRICKS TABLE : EMP
*  SAVE MODE : Overwrite
