Round Value
===========



Input
--------------
It takes in a DataFrame as input

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRoundDouble

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Column
        - The columns containing double or float values to round.
      * - precision
        - Precision
        - The scale of the double values to round to.


Details
-------
Round Value Node
+++++++++++++++


This node rounds numeric values in specified columns to a given precision.


Examples
-------
Round Value Node Example
+++++++++++++++


Given the following dataset:


SupplierID    SupplierName    Region    YearsInBusiness    LeadTime    PriceIndex    OrderFulfillmentTime    OverallCost    OrderCancellations    CustomerRating

S1    Supplier A    Region 1    10    5.32    1.2345    3    100.123    2    4


If you configure the Round Value node to round the PriceIndex column to 2 decimal places, the output would look like this:


SupplierID    SupplierName    Region    YearsInBusiness    LeadTime    PriceIndex    OrderFulfillmentTime    OverallCost    OrderCancellations    CustomerRating

S1    Supplier A    Region 1    10    5.32    1.23    3    100.12    2    4
