Filter By Date Range
=========== 

This node filters Rows within the given date range

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeFilterByDateRange

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCol
        - Column
        - input column name
      * - fromDateCol
        - From Date
        - Takes Start Date in the form of yyyy-MM-dd
      * - toDateCol
        - To Date
        - Takes End Date in the form of yyyy-MM-dd


Details
-------


Filter By Date Range Node Details
+++++++++++++++

This node filters Rows for the specified date range.

New outgoing Dataframe is created by applying Date Range filter on the selected column.

Input
```````````````

*    COLUMN :- Select a Date column on which filter is to be applied.
*    FROM DATE :- Select starting date of the Date Range filter. Date can be selected using the Calendar popup.
*    TO DATE :- Select ending date of the Date Range filter. Date can be selected using the Calendar popup.


Output
```````````````

*    It will filter rows by applying Date Range filter using 'FROM DATE' and 'TO DATE' on the date column.


Examples
-------


Filter By Date Range Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

CUST_CD    |    INV_NO    |    INV_DT      |    PRD_CD
----------------------------------------------------------
C01        |    INV1111   |    2021-10-01  |    PRD01
C01        |    INV1112   |    2021-10-03  |    PRD02
C01        |    INV1113   |    2021-10-05  |    PRD03
C01        |    INV1114   |    2021-10-07  |    PRD04
C01        |    INV1115   |    2021-10-09  |    PRD05
C01        |    INV1116   |    2021-10-10  |    PRD06

FilterByDateRange Node Configuration
```````````````

FilterByDateRange node is configured as below:

COLUMN       :    INV_DT_VAL
FROM DATE    :    2021-10-01
TO DATE      :    2021-10-05

FilterByDateRange Node Output
```````````````

Outgoing Dataframe would be created as below with the rows falling within the given date range:

CUST_CD    |    INV_NO    |    INV_DT      |    PRD_CD
----------------------------------------------------------
C01        |    INV1111   |    2021-10-01  |    PRD01
C01        |    INV1112   |    2021-10-03  |    PRD02
C01        |    INV1113   |    2021-10-05  |    PRD03
