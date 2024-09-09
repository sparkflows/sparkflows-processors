ExpectColumnValuesToNotBeNull
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToNotBeNull

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


Expect Column Values To Not Be Null Details
+++++++++++++++

Expect the column values to not be null.

To be counted as an exception, values must be explicitly null or missing, such as an np.NaN in pandas. Empty strings don't count as null unless they have been coerced to a null type.

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

EMP_CD    |    EMP_NAME    |
--------------------------------------
E01       |    DAVID       |
E02       |                |
E03       |    MARK        |
E04       |    JACK        |

Configuration
```````````````

Column Name   | Mostly  |
-------------------------
EMP_CD        |         |
EMP_NAME      | 0.8     |           

The above setup would result in a status of `success: false`, as even though the `EMP_CD` column value evaluates to be true it fails for the condition setup for the column `EMP_NAME`.  
