Word Count
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeWordCount

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - delimiter
        - Input Columns
        - 


Details
-------
Word Count Node
---------------


This node counts the number of words in the specified text column(s) of a dataset.


Examples
-------
Word Count Node Example
---------------


Given the following dataset:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

B2    S2    Nut and Bolt    Hardware    7

C3    S3    Screw    Hardware    9


If you configure the Word Count node to count the number of words in the PartName column, the output would look like this:


PartName    Word Count

Bolt    1

Nut and Bolt    3

Screw    1
