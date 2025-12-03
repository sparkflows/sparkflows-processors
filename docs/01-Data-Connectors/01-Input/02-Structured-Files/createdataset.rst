Create Dataset
=========== 

Creates a dataset with the specified number of rows and nine pre-defined columns

Input
--------------
It does not read data from any external source

Output
--------------
It creates a DataFrame with the specified number of rows

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetCreate

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - numRows
        - Number of Rows
        - Number of Rows in the Output Dataset


Details
===============
This node Creates a dataset with the specified number of rows and nine pre-defined columns.


Examples
===============
the node will give such table for the number of rows defined


id    column1    column2    column3    column4    column5    column6    column7    column8

long    double    integer    integer    integer    string    string    string    string

0    9.0    7    8    9    cc@abc.com    2018-03-10    Markita Hansen    10/03/2018

1    9.0    7    8    9    cc@abc.com    2018-03-10    Markita Hansen    10/03/2018

2    9.0    7    8    9    cc@abc.com    2018-03-10    Markita Hansen    10/03/2018
