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


Unix Time To String Details
+++++++++++++++

This Node converts the Unix timestamp to a String representing Date and Timestamp, in other words, it converts the Epoch time in seconds to date and timestamp.

Input
```````````````

*    INPUT COLUMN NAME :- Select the long datatype field which represents the Unix time.
*    OUTPUT COLUMN NAME :- Enter the output column name.
*    OUTPUT COLUMN FORMAT :- Specify the output column format.


Output
```````````````

*    Converts the Unix timestamp to a String representing Date and Timestamp in the given format.


Example
```````````````

*    Input column value:- 1293840120
*    Output column format :- yyyy-MM-dd HH:mm:ss

    The ouput would be 2011-01-01 00:02:00


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
