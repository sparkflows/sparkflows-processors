Filter By String Length
=========== 

This node filters the Rows within the given string length. The column to be used for determining the string length is specified.

Input
--------------
It accepts a DataFrame as input from the previous Node

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeFilterByStringLength

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCol
        - Input Column Name
        - input column name
      * - minLength
        - Minimum length
        - Minimum length of String
      * - maxLength
        - Maximum length
        - Maximum length of String


Details
-------


Filter By String Length Node Details
+++++++++++++++

This node filters Rows for the specified data length range. It helps to define a validation rule on the selected column.

New outgoing Dataframe is created by applying Data Length Range filter on the selected column. Outgoing Dataframe consists of rows where in Data Length of the specified column is within the defined Length Range.

Input
```````````````

*    INPUT COLUMN NAME :- Select a String column on which filter is to be applied.
*    MINIMUM LENGTH :- Enter starting value of the Data Length Range Filter.
*    MAXIMUM LENGTH :- Enter ending value of the Data Length Range Filter.


Output
```````````````

*    It will filter rows by applying Data Length Range filter using 'MINIMUM LENGTH' and 'MAXIMUM LENGTH' on the select column.


Examples
-------


Filter By String Length Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

EMP_CD    |    EMP_NAME    |    DEPT    |    SALARY    |    AGE    
------------------------------------------------------------------------
E01       |    ANTHONY     |    HR      |    50000     |    40
E02       |    LISA        |    HR      |    50000     |    35
E03       |    MARTIN      |    HR      |    20000     |    25
E04       |    DAVID       |    SALES   |    55000     |    40
E05       |    MARK        |    SALES   |    60000     |    45
E06       |    JOE         |    SALES   |    40000     |    25
E07       |    BELLA       |    HR      |    60000     |    24

FilterByStringLength Node Configuration
```````````````

FilterByStringLength node is configured as below:

INPUT COLUMN NAME    :    EMP_NAME
MINIMUM LENGTH       :    3
MAXIMUM LENGTH       :    5

FilterByStringLength Node Output
```````````````

Outgoing Dataframe would be created as below and consists of the rows falling within the given string length range:

EMP_CD    |    EMP_NAME    |    DEPT    |    SALARY    |    AGE    
------------------------------------------------------------------------
E02       |    LISA        |    HR      |    50000     |    35
E04       |    DAVID       |    SALES   |    55000     |    40
E05       |    MARK        |    SALES   |    60000     |    45
E06       |    JOE         |    SALES   |    40000     |    25
E07       |    BELLA       |    HR      |    60000     |    24
