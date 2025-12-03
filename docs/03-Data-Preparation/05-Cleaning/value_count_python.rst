Value count
=========== 

Counts value in columns using the specified input

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeValueCount

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
        - Input Columns for which unique values needs to be counted


Details
===============
Value Count Node
---------------


This node counts the frequency of unique values in the specified columns of a dataset.


Examples
===============
Value Count Node Example
---------------


Given the following dataset:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

B2    S2    Nut    Hardware    7

A1    S1    Bolt    Hardware    8

C3    S3    Screw    Hardware    9

A1    S1    Bolt    Hardware    8


If you configure the Value Count node to count the unique values in the PartID and PartCategory columns, the output would look like this:


Column Name    Value    Frequency

PartID    A1    3

PartID    B2    1

PartID    C3    1

PartCategory    Hardware    5
