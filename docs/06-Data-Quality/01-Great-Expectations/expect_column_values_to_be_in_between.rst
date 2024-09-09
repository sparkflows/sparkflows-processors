ExpectColumnValuesToBeInBetween
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToBeInBetween

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - cols
        - Column Name
        - The column name.
      * - min
        - Min
        - The minimum value for a column entry length.
      * - max
        - Max
        - The maximum value for a column entry length.


Details
-------


Expect Column Values To Between Details
+++++++++++++++

Expect the column entries to be between a minimum value and a maximum value (inclusive).

Keyword Args
```````````````

Column Name: The column name
Min (comparable type or None): The minimum value for a column entry.
Max (comparable type or None): The maximum value for a column entry.

Notes
```````````````
`Min` and `Max` are both inclusive.
If `Min` is None, then `Max` is treated as an upper bound, and there is no minimum value checked.
If `Max` is None, then `Min` is treated as a lower bound, and there is no maximum value checked.


Examples
-------


Example
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

EMP_CD    | Joining AGE   |    Joining Date     |
-------------------------------------------------
E01       |    42         | Jan 01 1979 12:00:01
E02       |    29         | Dec 31 1999 12:00:11
E03       |    35         | Jan 01 2000 12:03:01
E04       |    54         | Feb 01 2000 12:00:01	

Configuration #1
```````````````

Column Name | Min  | Max  |
--------------------------
Joining AGE | 25   | 60   |

The above setup would result in a status of `success: true` as the condition is satisfied.

Configuration #2
```````````````

Column Name  |          Min           |          Max           |
----------------------------------------------------------------
Joining Date | Jan 01 1990 12:00:00   | Jan 01 2001 12:00:00   |

The above setup would result in a status of `success: false` as the condition is satisfied.
