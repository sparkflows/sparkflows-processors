Count Null Values
=========== 

Counts null value in columns using the specified input

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeNullCount

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Input Columns for which the number of nulls needs to be counted


Details
===============
Count Null Values Node
---------------


This node counts the number of null values in each specified column of a dataset.


Examples
===============
Count Null Values Node Example
---------------


Given the following dataset:


id    column1    column2    column3    column4    column5    column6    column7    column8

1    10.2    5    null    20    "A"    null    "C"    "D"

2    null    6    15    30    "B"    "E"    null    null

3    12.3    null    25    40    null    "F"    "G"    "H"


If you configure the Count Null Values node to count null values in all columns, the output would look like this:


Column Name    Number of Null Values

id    0

column1    1

column2    1

column3    1

column4    0

column5    1

column6    1

column7    1

column8    2
