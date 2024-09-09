Node Row Filter By Index
=========== 

This node creates a new DataFrame containing only rows satisfying given condition

Input
--------------
It accepts DataFrame as input from the previous Node

Output
--------------
This node filters the rows based on the conditional expression to generate the output DataFrame

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRowFilterByIndex

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - indexes
        - Indexes
        - Comma separated index values starts from 0. ex: 0, 1, 2, 5
      * - indexesRange
        - IndexesRange
        - Index ranges example like 10-14 i.e 10, 11, 12, 13, 14.


Details
-------


Node Row Filter By Index Node Details
+++++++++++++++

This node filters Rows for the specified Row Index numbers or the specified Row Index Range.

New outgoing Dataframe is created by selecting only the rows at the sepecified Index positions or falls within the specified Index Range. Index value starts with 0.

Input
```````````````

*    INDEXES :- Enter Index values of the rows that need to be included in the outgoing Dataframe. Example -> 0, 3, 2, 10
*    INDEXES RANGE :- Enter a range of Index values of the rows that need to be included in the output Dataframe. Example -> 0-10


Output
```````````````

*    Outgoing Dataframe would be created with the rows at the entered Indexes or within the Index Range.


Examples
-------


Node Row Filter By Index Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY
-------------------------------------------------------------------------------------
C01        |    MATT         |    50     |    12-02-2002         |    USD 200000.00
C02        |    LISA         |    45     |    15-11-2020         |    GBP 100000.00
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00
C04        |    MARCUS       |    35     |    01-01-2021         |    AUD 350000.00

Node Row Filter By Index Node Configuration And Output
```````````````

[0,2] is entered in the Indexes field to filter Rows By Index.
Outgoing Dataframe would be created as below containing only the selected columns:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY
-------------------------------------------------------------------------------------
C01        |    MATT         |    50     |    12-02-2002         |    USD 200000.00
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00

Node Row Filter By Index Node Configuration And Output
```````````````

[1-3] is entered in the Index Range field to filter Rows By Index.
Outgoing Dataframe would be created as below containing only the selected columns:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY
-------------------------------------------------------------------------------------
C02        |    LISA         |    45     |    15-11-2020         |    GBP 100000.00
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00
C04        |    MARCUS       |    35     |    01-01-2021         |    AUD 350000.00
