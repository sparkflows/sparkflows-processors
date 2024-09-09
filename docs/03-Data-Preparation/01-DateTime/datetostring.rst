Date To String
=========== 

This node converts a date/time column to string with given format

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeMultiDateToString

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputColNames
        - Input Column Name
        - Input Column Name
      * - outputColFormats
        - Output Column Formats
        - Output Column Formats. eg: yyyy-MM-dd yyyy-MM-dd HH:mm:ss
      * - outputColNames
        - Output Column Names
        - Output Column Names


Details
-------


Date To String Details
+++++++++++++++

This node converts the Date or Timestamp column to string datatype format.

Input
```````````````

*    INPUT COLUMN NAME :- Select the Date/Timestamp datatype which needs to be converted to a string.
*    OUTPUT COLUMN FORMATS :-Specify the output String format.
*    OUTPUT COLUMN NAMES :- Specify the new column name.


Output
```````````````

*    It will generate a new Dataframe with a specified column that will contain the specified String format value.


Example
```````````````

*   Input:2011-01-29
*   OUTPUT COLUMN FORMATS : dd/mm/yyyy

   The output would be 29/01/2011 


*   Input:2011-01-29
*   OUTPUT COLUMN FORMATS : yyyy-MM-dd HH:mm:ss

   The output would be 2011-01-29 00:00:00 


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
