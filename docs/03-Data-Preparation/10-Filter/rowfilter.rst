Row Filter
=========== 

This node creates a new DataFrame containing the rows that satisfy the given condition

Input
--------------
It accepts DataFrame as input from the previous Node

Output
--------------
This node filters the rows based on the conditional expression to generate the output DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRowFilter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - conditionExpr
        - Conditional Expression
        - The filtering condition. Rows not satisfying given condition will be excluded from output DataFrame. eg: usd_pledged_real > 0 and (category = 1 or category == 2) and goal > 100


Details
-------


Details
+++++++++++++++

Row filter allows the user to filter out rows that do not meet a set condition. Rows that meet the condition are passed on to the next node in a new dataframe. 


Examples
-------


Examples of Conditional Expression
+++++++++++++++

Below are some examples of the Conditions Expression which can be used.


*  col1 > 5 AND col2 > 3



*  name is not NULL



*  name is NULL



*  usd_pledged_real > 0 and (category = "Narrative Film" or category == "Music") and goal > 100



*  dt > '2021-09-03'  (dt column is of type date)



*  datetime > '2011-01-01 00:00:00.0'     (datetime column is of type timestamp)



*  datetime > '2011-01-01 00:00:00.0' and datetime < '2016-01-01 00:00:00.0'
