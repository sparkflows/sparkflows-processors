SQL Transformer
=========== 

This node runs the given SQL on the incoming DataFrame using Spark ML SQLTransformer

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeSQLTransformer

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - tempTable
        - Temp Table
        - Temp Table Name to be used
      * - sql
        - SQL
        - SQL to be run
      * - outputColNames
        - Output Column Names
        - Name of the Output Columns
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns


Details
-------


 SQL Transformer Node Details
+++++++++++++++

The SQL Transformer Node implements the transformations which are defined by SQL statement. Currently,  supports SQL syntax like 

*  SELECT a, a + b AS ab FROM  tablename
*  SELECT a, SQRT(b) AS bsqrt FROM tablename where a > 5
*  SELECT a, b, SUM(c) AS csum FROM tablename GROUP BY a, b


Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TEMP TABLE : Defaults to 'fire_temp_table'. A name provided for the underlying table of the input dataset.
*  SQL : Enter the SQL statement for execution. The select clause specifies the fields, constants, and expressions to display in the output, and can be any select clause that Spark SQL supports. 


Examples
-------


 SQL Transformer Node Example
+++++++++++++++

Assume that we have the following DataFrame with columns id, v1 and v2:

id  | v1  | v2
----|-----|-----
100 | 1.0 | 3.0
200 | 2.0 | 5.0

This is the output of the SQLTransformer with statement "SELECT *, (v1 + v2) AS v3, (v1 * v2) AS v4 FROM fire_temp_table" entered in the <b>SQL</b> box:

 id |  v1 |  v2 |  v3 |  v4
----|-----|-----|-----|-----
 0  | 1.0 | 3.0 | 4.0 | 3.0
 2  | 2.0 | 5.0 | 7.0 |10.0
