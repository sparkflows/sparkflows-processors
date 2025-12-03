Sample
=========== 

Samples the incoming DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeSample

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - withReplacement
        - With Replacement
        - With or without Replacement
      * - fraction
        - Fraction
        - Fraction
      * - seed
        - Seed
        - Seed


Details
===============
Sample Node
---------------


This node samples a specified fraction of rows from the input DataFrame. It can be used for various purposes, such as reducing dataset size for testing or exploratory analysis.


Examples
===============
Sample Node Example
---------------


Given the following dataset:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

B2    S2    Nut    Hardware    7

C3    S3    Screw    Hardware    9

...    ...    ...    ...    ...


If you configure the Sample node to sample 0.2(20%) of the rows with replacement, the output might look like this:


PartID    SupplierID    PartName    PartCategory    PartQualityScore

A1    S1    Bolt    Hardware    8

C3    S3    Screw    Hardware    9

A1    S1    Bolt    Hardware    8

...    ...    ...    ...    ...
