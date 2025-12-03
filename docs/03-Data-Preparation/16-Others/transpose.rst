Transpose
=========== 

This node transposes a dataframe without performing aggregation function by given column(transposeby). ALL INPUT COLUMNS TO THIS NODE HAVE TO BE OF THE SAME TYPE

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
Output dataframe consisting of three columns transposeBy, column_name, column_value

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeTranspose

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - transposeBy
        - Transpose By Column Name
        - transposeBy column name


Details
===============
Transpose Node
---------------


This node transposes the rows and columns of a DataFrame on the selected column, effectively pivoting the data. It's useful for reshaping data into a different format.


Examples
===============
Transpose Node Example
---------------


Given the following dataset:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

B2    S2    Nut    Hardware    7

C3    S3    Screw    Hardware    9


If you configure the Transpose node to transpose the DataFrame by the PartID column, the output would look like this:


Column Name    A1    B2    C3

SupplierID    S1    S2    S3

PartName    Bolt    Nut    Screw

PartCategory    Hardware    Hardware    Hardware

PartQualityScore    8    7    9
