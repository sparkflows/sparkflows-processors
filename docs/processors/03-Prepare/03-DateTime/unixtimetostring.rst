Unix Time To String
=========== 

This node converts Unix Time to String

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeUnixTimeToString

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
        - input column name
      * - outputColName
        - Output Column Name
        - Output Column Name
      * - outputColFormat
        - Output Column Format
        - Output Column Format (eg: yyyy-MM-dd HH:mm:ss)


Details
-------


This node converts unix time (seconds) to string type.


Examples
-------


Format Examples
+++++++++++++++


*  dd-MM-yy : 31-01-12
*  dd-MM-yyyy : 31-01-2012
*  MM-dd-yyyy : 01-31-2012
*  yyyy-MM-dd : 2012-01-31
*  yyyy-MM-dd HH:mm:ss : 2012-01-31 23:59:59
*  yyyy-MM-dd HH:mm:ss.SSS : 2012-01-31 23:59:59.999
*  yyyy-MM-dd HH:mm:ss.SSSZ : 2012-01-31 23:59:59.999+0100
*  EEEEE MMMMM yyyy HH:mm:ss.SSSZ : Saturday November 2012 10:45:42.720+0100


Example:
select an input column (long type), output column name and desired output column format.
It will add one more column in string format. 

If you input a date format like dd-MM-yy. It will add one column having value like 31-01-12.
