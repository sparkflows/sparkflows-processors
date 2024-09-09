ExpectColumnValuesToBeNull
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToBeNull

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
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
-------


Expect Column Values To Be Null Details
+++++++++++++++

Expect the column values to be null.

Keyword Args
```````````````

Column Name: The column name
Mostly (None or a float between 0 and 1): Return `success`: True if at least mostly fraction of values match the expectation.


Examples
-------


Example
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

EMP_CD    |    DEPT        |
--------------------------------------
E01       |                |
E02       |                |
E03       |                |
E04       |                |

Configuration #1
```````````````

Column Name   | Mostly  |
-------------------------
EMP_CD        |         |

The above setup would result in a status of `success: false` as the condition is not satisfied.

Configuration #2
```````````````

Column Name   | Mostly  |
-------------------------
DEPT        |   0.9     |

The above setup would result in a status of `success: true` as the condition is satisfied.
