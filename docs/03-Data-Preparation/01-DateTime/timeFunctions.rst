Time Functions
=========== 

This node extracts year, dayofmonth, dayofyear, weekofyear, dayofweek, quarter, hour, minute, second & season.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeTimeFunctions

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - timeStampCol
        - TimeStamp Column Name
        - input column name
      * - timeFunctions
        - Time Functions
        - Time Functions Name


Details
-------


Time Functions Details
+++++++++++++++

This node can be used to extract year, dayofmonth, dayofyear, weekofyear, dayofweek, quarter, hour, minute, second & season values from a Timestamp column.


Input
```````````````

*    TIMESTAMP COLUMN NAME :-The input column is selected here and it should be of Timestamp or Date type


Output
```````````````

*    The values that can be selected are Year, DayOfMonth, DayOfYear, WeekOfYear, DayOfWeek, Quarter, Hour, Minute, Second & Season.
*    These values are created as new columns of the Output DataFrame.


Example
```````````````

*    InputColumn Value :- 2022-01-29
*    Selected Options :- Season,Quarter,DayOfMonth
*    Output would be InputColumn_season :- Winter   InputColumn_quarter :-	1    InputColumn_dayofmonth :-29


Examples
-------


If Incoming Dataframe has following timestamp column:

INV_DATE
-------------------------------------------
2022-07-01 10:11:12.0

after execution of TimeFunctions node following columns would get added to the outgoing Dataframe for the above row:

COLUMN_NAME             |    VALUE
----------------------------------------
INV_DATE_year           |    2022
INV_DATE_month          |    7
NV_DATE_dayofmonth      |    1
INV_DATE_dayofyear      |    182
INV_DATE_weekofyear     |    26
INV_DATE_dayofweek      |    5
INV_DATE_quarter        |    3
INV_DATE_hour           |    10
INV_DATE_minute         |    11
INV_DATE_second         |    12
INV_DATE_season         |    Summer
