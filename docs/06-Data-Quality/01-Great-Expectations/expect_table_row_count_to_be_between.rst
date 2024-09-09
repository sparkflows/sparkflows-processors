ExpectTableRowCountToBeBetween
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectTableRowCountToBeBetween

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - min
        - Min Count
        - 
      * - max
        - Max Count
        - 


Details
-------


Expect Table Row Count To Be Between Details
+++++++++++++++

Expect the number of rows to be between two values.

Keyword Args
```````````````

Min Count : The minimum number of rows, inclusive.
Max Count : The maximum number of rows, inclusive.

 Notes
```````````````
`Min Count` and `Max Count` are both inclusive.
If `Min Count` is None, then `Max Count` is treated as an upper bound, and the number of acceptable rows has no minimum.
If `Max Count` is None, then `Min Count` is treated as a lower bound, and the number of acceptable rows has no maximum.


Examples
-------


Expect Table Row Count To Be Between Example
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

EMP_CD    |    EMP_NAME    |    DEPT
--------------------------------------
E01       |    DAVID       |    
E02       |    JANE        |    
E03       |    MARK        |
E04       |    JACK        |

Expect Table Row Count To Be Between Node Configuration
```````````````

Min Count   |    Max Count   
-----------------------------
3           |    5          |       

The above setup would result in a status of `success: true`, as the number of records in the table is 4 which lies between the count of the configured minimum and maximum value.  
