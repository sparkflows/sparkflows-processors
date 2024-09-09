Filter By Number Range
=========== 

This node filters the rows in the given Number Range

Input
--------------
It accepts a DataFrame as input from the previous Node

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeFilterByNumberRange

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
      * - lowestValue
        - Lowest Value
        - input lowest value
      * - highestValue
        - Highest Value
        - input highest value


Details
-------


Filter By Number Range Node Details
+++++++++++++++

This node filters Rows for the specified number range. It helps to define a validation rule on the selected column.

New outgoing Dataframe is created by applying Number Range filter on the selected column.

Input
```````````````

*    INPUT COLUMN NAME :- Select a Number column on which filter is to be applied.
*    LOWEST VALUE :- Enter starting value of the Number Range Filter.
*    HIGHEST VALUE :- Enter ending value of the Number Range Filter.


Output
```````````````

*    It will create an output dataframe with rows falling in the given number range between 'LOWEST VALUE' and 'HIGHEST VALUE' column. 


Examples
-------


Filter By Number Range Node Examples
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

FilterByNumberRange Node Configuration
```````````````

FilterByNumberRange node is configured as below:

INPUT COLUMN NAME    :    AGE
LOWEST VALUE         :    35
HIGHEST VALUE        :    45

FilterByNumberRange Node Output
```````````````

Outgoing Dataframe would be created as below with rows falling within the given number range:

EMP_CD    |    EMP_NAME    |    DEPT    |    SALARY    |    AGE    
------------------------------------------------------------------------
E01       |    ANTHONY     |    HR      |    50000     |    40
E02       |    LISA        |    HR      |    50000     |    35
E04       |    DAVID       |    SALES   |    55000     |    40
E05       |    MARK        |    SALES   |    60000     |    45
