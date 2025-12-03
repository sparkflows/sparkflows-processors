Standard Deviation
===========

Creates new columns using the specified input columns

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeStandardDeviation

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
        - columns for computing standard deviation


Details
-------
Standard Deviation Node
+++++++++++++++


This node calculates the standard deviation for the specified numeric columns in a dataset. The standard deviation is a measure of how spread out the values are from the mean.


Examples
-------
Standard Deviation Node Example
+++++++++++++++


Given the following dataset:


id    column1    column2    column3    column4    column5    column6    column7    column8

1    10.2    5    12    20    "A"    "B"    "C"    "D"

2    11.3    6    15    30    "A"    "B"    "C"    "D"

3    12.4    7    18    40    "A"    "B"    "C"    "D"


If you configure the Standard Deviation node to calculate the standard deviation for column1, column2, column3, and column4, the output would look like this:


Column Name    Standard Deviation

column1    1.005

column2    1.000

column3    1.500

column4    10.000
