ExpectColumnValueLengthToBeInBetween
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValueLengthToBeInBetween

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
===============
Expect Column Value length To be in Between Details
---------------


Expect the column value lengths to be between a minimum value and a maximum value (inclusive).



Keyword Args
+++++++++++++++


Column Name: The column name

Min (comparable type or None): The minimum value for a column entry.

Max (comparable type or None): The maximum value for a column entry.



Notes
+++++++++++++++

`Min` and `Max` are both inclusive.

If `Min` is None, then `Max` is treated as an upper bound, and there is no minimum value checked.

If `Max` is None, then `Min` is treated as a lower bound, and there is no maximum value checked.


Examples
===============
If the incoming DataFrame has the following values in column6:


column6

apple

orange

pineapple

kiwi

banana

Setting Min to 5 and Max to 7 will yield the following result:


Valid values: "orange" and "banana"

Invalid values: "apple" (too short), "pineapple" (too long), "kiwi" (too short)
