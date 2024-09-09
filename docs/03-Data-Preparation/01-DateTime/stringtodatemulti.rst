String To Date
=========== 

This node converts string columns to date using the specified date/time format

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeMultiStringToDate

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputColNames
        - Columns
        - Columns
      * - inputColFormats
        - Input Column Formats
        - Input Column Formats. eg: yyyy-MM-dd yyyy-MM-dd HH:mm:ss
      * - outputColNames
        - Output Column Names
        - Output Column Names
      * - outputColTypes
        - New Data Types
        - New data types (DATE, TIMESTAMP)


Details
-------


String To Date Multi Details
+++++++++++++++

This node converts a string column to a date or timestamp datatype column. This node can be used to convert multiple string columns to new Date or Timestmp columns. 

Input
```````````````

*    COLUMNS :- Select the String field(s) which needs to be converted.
*    INPUT COLUMN FORMATS :-The format of the input column is specified here.
*    OUTPUT COLUMN NAMES :- Specify the output column name for the converted value. 
*    NEW DATA TYPES :- Select the output type as either of DATE or TIMESTAMP datatype.


Output
```````````````

*    It will convert all the specified columns into the specified  datatype.


Example
```````````````

*    Input : 04/13/2019
*    Format : MM/dd/yyyy
*    NEW DATA TYPES : DATE

    The Output value would be 2019-04-13 which is of DATE datatype


*    Input : 04/13/2019
*    Format : MM/dd/yyyy
*    NEW DATA TYPES : TIMESTAMP

    The Output value would be 2019-04-13 00:00:00 which is of TIMESTAMP datatype


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
