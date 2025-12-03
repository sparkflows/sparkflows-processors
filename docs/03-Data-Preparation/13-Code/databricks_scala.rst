Scala
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

fire.nodes.code.NodeDataBricksScala

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
        - Scala code to be run. Input dataframe : "inDF", SparkContext : "sc", SQLContext : "sqlContext", Output/Result dataframe should be registered as a temporary table - df.registerTempTable("outDF")
      * - schema
        - InferSchema
        - 
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
===============
Scala Details
---------------


This node receives receives an input dataframe.

The input dataframe is passed into the Scala code as a variable called inDF.


The scala code operates on the dataframe inDF.

Finally the scala code produces a resulting dataframe to be passed on to the next node. It does so by registering a temporary table called outDF.


Examples
===============
Scala Examples
---------------



Calculate Count of Houses by Bathrooms
+++++++++++++++



* val outDF = inDF.groupBy("bathrms").count()
* outDF.registerTempTable("outDF")


registerTempTable is used to register the result dataframe as a temporary table. The output table name has to be outDF.
