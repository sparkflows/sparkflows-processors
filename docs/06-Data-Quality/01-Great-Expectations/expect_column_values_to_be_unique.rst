ExpectColumnValuesToBeUnique
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToBeUnique

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


Expect Column Values To Be Unique Details
+++++++++++++++

Expect each column value to be unique.

This expectation detects duplicates. All duplicated values are counted as exceptions.

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
E01       |    MARKETING   |
E02       |    MARKETING   |
E03       |    SALES       |
E04       |    ADMIN       |

Configuration
```````````````

Column Name   | Mostly  |
-------------------------
EMP_CD        |         |
DEPT          | 0.75    |           

The above setup would result in a status of `success: true` as both conditions are satisfied.
