Date To Age
=========== 

This node converts a date-column into columns of age (both in years and in days).

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDateToAge

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputColName
        - Input Column Name
        - Input Column Name
      * - yearsOutputColName
        - Years Output Column Name
        - Num Years Output Column Name
      * - daysOutputColName
        - Days Output Column Name
        - Num Days Output Column Name


Details
-------


Date To Age Details
+++++++++++++++

Calculates current age in years and in days from the selected date or timestamp field.

Input
```````````````

*  INPUT COLUMN NAME :- Select the Date\TimeStamp field for which we want to calculate the current age.
*  YEARS OUTPUT COLUMN NAME :- Specify the output column name for years column, the output will provide the number of years between the selected input column and today.
*  DAYS OUTPUT COLUMN NAME :- Specify the output column name for days column, it will provide the output in terms of number of days from the selected input column till date.


Output
```````````````

*  Two new columns will be created, One for <b>years</b> and the other for <b>days</b>. 
*  Example :- When the current date is 06-25-2019 then the age difference for the below input value would be:

  dd-MM-yyyy : 20-09-2018 , 0 year : 278 days


Examples
-------


Examples when date is 06-25-2019
+++++++++++++++


*  dd-MM-yyyy : 20-09-2018 , 0 year : 278 days
*  MM-dd-yyyy : 09-30-2018 , 0 year : 268 days
*  yyyy-MM-dd : 2012-01-31 , 7	year : 2702 days
