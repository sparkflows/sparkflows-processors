MultiInputPySpark
=========== 

This node runs any given PySpark code. The input dataframes is passed in the variable inDFs. The output dataframe is passed back by registering it as a temporary table.

Input
--------------
The input dataframes is passed in the variable inDFs.

Output
--------------
The output dataframe is passed back by registering it as a temporary table

Type
--------- 

pyspark2inputs

Class
--------- 

fire.nodes.code.NodeMultiInputPySpark

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - code
        - PySpark
        - PySpark code to be run. Input dataframe : "inDF", SparkContext : "sc", SQLContext : "sqlContext",  Output/Result dataframe should be registered as a temporary table - df.registerTempTable("outDF")
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


Pyspark Details
+++++++++++++++

This node receives input pyspark dataframes in function called myfn.

The pyspark/python code processes it and returns one computed pyspark dataframe.


Examples
-------


Pyspark Examples
+++++++++++++++

Input Schema of dataframe.

Input Schema of first dataframe: id, price, lotsize, bedrooms, bathrms, stories, driveway, recroom, fullbase, gashw, airco, garagepl, prefarea

Input Schema of second dataframe: id, price, lotsize, bedrooms, bathrms, stories, driveway, recroom, fullbase, gashw, airco, garagepl, prefarea

 Add the house_type column
```````````````

from pyspark.sql.types import StringType
from pyspark.sql.functions import *
from pyspark.sql import *
from fire.workflowcontext import *

def myfn(spark: SparkSession, workflowContext: WorkflowContext, id: int, inDFs:[DataFrame], cust_dict:dict):

#get the first dataframe
df1 = inDFs[0]

#get the second dataframe
df2 = inDFs[1]

# Join the two dataframes
outdf = df1.join(df2, ['id'])

return outdf
