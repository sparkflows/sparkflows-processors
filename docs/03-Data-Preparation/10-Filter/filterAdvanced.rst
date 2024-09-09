Filter Advanced
=========== 

This node generates two new DataFrames: one containing rows that meet the specified condition at the lower edge, and the other containing rows that fail to meet the condition at the higher edge.

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

fire.nodes.etl.NodeFilterAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - basic
        - Basic Filter
      * - inputCol
        - Input Column
        - input column name
      * - operator
        - Expression
        - choose the expression
      * - conditionValue
        -  Condition Value
        - condition value
      * - date
        - Date Filter
      * - inputDateCol
        - Input Date Column
        - Input Date Column Name
      * - filterBy
        - Filter By
        - choose the filter
      * - startDate
        - Start Date
        - Takes Start Date in the form of yyyy-MM-dd
      * - endDate
        - End Date
        - Takes End Date in the form of yyyy-MM-dd
      * - periodType
        - Period Type
        - choose the expression
      * - numPeriods
        - Number of Periods
        - Number of Periods
      * - custom
        - Custom Filter
      * - conditionExpr
        - Conditional Expression
        - The filtering condition. Rows not satisfying given condition will be excluded from output DataFrame. eg: usd_pledged_real > 0 and (category = 1 or category == 2) and goal > 100


Details
-------


 Filter Advanced Details
+++++++++++++++

The Advanced Filter allows the user to filter out rows that meet a specific condition. This filtering can be performed using either the Basic Filter, Date Filter, or Custom Filter options.
This Node outputs two dataframe. Lower Edge outputs the filtered data and the Higher Edge outputs remaining data.


Examples
-------

Examples of Basic Filter
+++++++++++++++

Example1:
Input Configrations:

Input Column:"Index"
Operator:"<="
Condition Value:"5"

This would filter out rows where index is less than or equal to 5.

Input Dataframe :
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Example2:
Input Configrations:

Input Column:"name"
Operator:"<="
Condition Value:"Frank"

This configuration will select all the rows where the name is less than or equal to 'Frank' based on lexicographical ordering.

* *Note**: If the condition is name <= 'F', it will filter the rows where the value of the "name" column is less than or equal to 'F' based on lexicographical ordering. (The row with the name "Frank" will be excluded.)

Input Dataframe:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Example3:
Input Configrations:

Input Column:"name"
Operator:"isNull"
Condition Value:"5"

This would filter out rows where name is null.

Input Dataframe :
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  null |2011-02-19|
|    9|  null |2019-10-04|
|   10|  null |1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    8|  null |2011-02-19|
|    9|  null |2019-10-04|
|   10|  null |1999-02-23|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
+-----+-------+----------+


Examples of Date Filter
+++++++++++++++
Example1:

Input Configrations:
Input Date Column:"birthdate"
Filter By:"Range"
Start Date:"1993-02-22"
End Date:"2000-02-22"
Period Type:""
Number of Periods:""

Input Dataframe:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    2|    Bob|1999-07-24|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
+-----+-------+----------+

Example2:

Input Configrations:
Input Date Column:"birthdate"
Filter By:"Start Date and Period After"
Start Date:"1992-01-21"
End Date:""
Period Type:"Months"
Number of Periods:"5"
This configration will filter out data from start date to 5 months after start date

Input Dataframe:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    3|Charlie|1992-03-28|
|    6|  Frank|1992-02-24|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+
Example3:

Input Configrations:
Input Date Column:"birthdate"
Filter By:"End Date and Period Before"
Start Date:""
End Date:"2000-12-31"
Period Type:"Years"
Number of Periods:"10"
This configration will filter out data from end date to 10 years before end date

Input Dataframe:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    4|  David|2006-11-06|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the lower edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    2|    Bob|1999-07-24|
|    3|Charlie|1992-03-28|
|    5|    Eva|1992-12-29|
|    6|  Frank|1992-02-24|
|   10|   Jack|1999-02-23|
+-----+-------+----------+

Output Dataframe in the higher edge:
+-----+-------+----------+
|index|   name| birthdate|
+-----+-------+----------+
|    1|  Alice|2014-08-31|
|    4|  David|2006-11-06|
|    7|  Grace|2006-01-07|
|    8|  Henry|2011-02-19|
|    9|    Ivy|2019-10-04|
+-----+-------+----------+


Examples of Custom Filter
+++++++++++++++

Below are some examples of the Conditions Expression which can be used.


*  col1 > 5 AND col2 > 3



*  name is not NULL



*  name is NULL



*  usd_pledged_real > 0 and (category = "Narrative Film" or category == "Music") and goal > 100



*  dt > '2021-09-03'  (dt column is of type date)



*  datetime > '2011-01-01 00:00:00.0'    (datetime column is of type timestamp)



*  datetime > '2011-01-01 00:00:00.0' and datetime < '2016-01-01 00:00:00.0'
