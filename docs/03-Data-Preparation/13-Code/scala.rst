Spark
=========== 

This node runs any given Scala code. The input dataframe is passed in the variable inDF. The output dataframe is passed back by registering it as a temporary table.

Input
--------------
The input dataframe is passed in the variable inDF.

Output
--------------
The output dataframe is passed back by registering it as a temporary table

Type
--------- 

scala

Class
--------- 

fire.nodes.code.NodeSpark

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outTempTable
        - Output Temp Table
        - Output Temp Table
      * - code
        - Scala
        - Scala code to be run. Input dataframe : "inDF", SparkContext : "sc", SQLContext : "sqlContext",  Output/Result dataframe should be registered as a temporary table - df.registerTempTable("outDF")
      * - schema
        - Schema
      * - outputColNames
        - Column Names for the CSV
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types for the CSV
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the CSV
        - Format of the Output Columns


Details
-------


Scala Details
+++++++++++++++

This node receives receives an input dataframe.
The input dataframe is passed into the Scala code as a variable called inDF.

The scala code operates on the dataframe inDF.
Finally the scala code produces a resulting dataframe to be passed on to the next node. It does so by registering a temporary table called outDF.

For DataSet support add below import stmt:
import spark.implicits._


Examples
-------


Scala Examples
+++++++++++++++

Pass the Input dataframe as Output dataframe.
```````````````
In OUTPUT TEMP TABLE field add the name of the temp table. ex: temp_table


*  val outDF = inDF
*  outDF.registerTempTable("temp_table")


Calculate Count of Houses by Bathrooms
```````````````
In OUTPUT TEMP TABLE field add the name of the temp table. ex: temp_table


*  val outDF = inDF.groupBy("bathrms").count()
*  outDF.registerTempTable("temp_table")


registerTempTable is used to register the result dataframe as a temporary table. Use the `OUTPUT TEMP TABLE` field name for that.
