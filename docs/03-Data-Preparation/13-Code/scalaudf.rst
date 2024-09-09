Scala UDF
=========== 

This node runs any given Scala code for UDFs

Input
--------------
.

Type
--------- 

scala

Class
--------- 

fire.nodes.etl.NodeUDFScala

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - code
        - Scala
        - Scala code to be run.


Details
-------


Scala UDF Details
+++++++++++++++

This node is used to run any given Scala code for User Defined Functions (UDFs).

UDFs are functions that can be used within Spark SQL statements to process data.
In this node, you can define your UDF code in the field "Scala". The code should be a valid Scala function that can be applied to a column of a dataframe.


Examples
-------


Scala UDF Examples
+++++++++++++++

Convert Celsius to Fahrenheit
```````````````

import org.apache.spark.sql.functions._
def celsiusToFahrenheit(temp: Double): Double = {
temp * 9/5 + 32
}
val celsiusToFahrenheitUDF = udf(celsiusToFahrenheit _)
In this example, we define a Scala function to convert temperatures from Celsius to Fahrenheit. This function is then converted into a UDF using the udf function from the Spark SQL functions package.
