Record ID
===========

Adds a sequential Record ID column to the dataset, similar to Alteryx Record ID Tool. Supports grouping, sorting, and formatted incremental IDs.

Input
--------------
Accepts a DataFrame as input.

Output
--------------
Returns a DataFrame with a new Record ID column added.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeGenerateRecordID

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCol
        - Output Column Name
        - Name of the column that will contain generated Record IDs.
      * - startValue
        - Starting Value
        - The first value in the sequence. Default is 1.
      * - dataType
        - Data Type
        - Select the data type of the Record ID column.
      * - size
        - Size (String Only)
        - Applicable only when Data Type is String. Pads the value with leading zeros to match this length.
      * - position
        - Column Position
        - Position of the new column in the output DataFrame.
      * - generationScope
        - Record ID Generation Scope
        - Generate IDs across the entire dataset or restart numbering within each group.
      * - groupByCols
        - Group By Columns
        - Columns to group by when generating Record IDs within groups.
      * - orderByCols
        - Order Rows Within Each Group
        - Optional columns to define the order of rows within each group before numbering. Supports ascending or descending order.


Details
-------
Record ID Node Details
+++++++++++++++

The Record ID Node generates a unique sequential identifier for each row in a DataFrame, similar to the Alteryx Record ID Tool. It supports flexible configuration, including grouping, sorting, and formatting, making it useful for adding row indexes or uniquely identifying records across or within groups.



General:
+++++++++++++++



Output Column Name:
+++++++++++++++

Specifies the name of the new column that will contain generated Record IDs. Example: "RecordID" or "RowNumber".



Starting Value:
+++++++++++++++

Specifies the initial number in the sequence. Default is 1. Example: Setting 1000 will start IDs from 1000.



Data Type:
+++++++++++++++

Determines the data type of the Record ID column. Options include:


* Int32: Generates 32-bit integer IDs.
* Int64: Generates 64-bit integer IDs.
* String: Generates IDs as strings (supports zero-padding when "Size" is specified).


Size (String Only):
+++++++++++++++


Specifies the number of characters for each Record ID when Data Type is set to "String". IDs are padded with leading zeros to match this length. Example: Size=6 produces IDs like "000001", "000002", etc.



Column Position:
+++++++++++++++

Defines where to insert the Record ID column in the output DataFrame. Options:


* first: Adds Record ID as the first column.
* last: Adds Record ID as the last column (default).


Record ID Generation Scope:
+++++++++++++++


Specifies how Record IDs are generated across the dataset:


* entire_table: IDs are assigned sequentially across all rows.
* within_group: IDs restart from the start value within each group defined by Group By Columns.


Group By Columns:
+++++++++++++++


Specifies one or more columns used to group rows. Record IDs reset for each group. Example: "Department" groups data by department before generating IDs.



Order Rows Within Each Group:
+++++++++++++++

Specifies columns used to order rows before assigning IDs. This supports ascending or descending order notation, e.g., "date asc, amount desc".



Output:
+++++++++++++++

The node returns a DataFrame identical to the input but with an additional column containing generated Record IDs. The output respects ordering and grouping configurations.


Examples
-------
Example: Record ID Node
+++++++++++++++



Example 1: Sequential IDs for Entire Dataset
+++++++++++++++



Input:
+++++++++++++++

::

    | Name  | Department |
    |--------|-------------|
    | John  | HR          |
    | Mary  | IT          |
    | Steve | HR          |



Configuration:
+++++++++++++++


* Output Column Name: RecordID
* Starting Value: 1
* Data Type: Int64
* Column Position: last
* Generation Scope: entire_table


Output:
+++++++++++++++

::

    | Name  | Department | RecordID |
    |--------|-------------|----------|
    | John  | HR          | 1        |
    | Mary  | IT          | 2        |
    | Steve | HR          | 3        |


::

    ---



Example 2: Group-wise Record ID Generation
+++++++++++++++



Input:
+++++++++++++++

::

    | Name  | Department |
    |--------|-------------|
    | John  | HR          |
    | Mary  | HR          |
    | Steve | IT          |
    | Alice | IT          |



Configuration:
+++++++++++++++

* Output Column Name: EmpID
* Starting Value: 1
* Data Type: Int32
* Generation Scope: within_group
* Group By Columns: Department


Output:
+++++++++++++++

::

    | Name  | Department | EmpID |
    |--------|-------------|-------|
    | John  | HR          | 1     |
    | Mary  | HR          | 2     |
    | Steve | IT          | 1     |
    | Alice | IT          | 2     |


::

    ---



Example 3: String-formatted Record IDs with Zero Padding
+++++++++++++++



Input:
+++++++++++++++

::

    | Product | Price |
    |----------|--------|
    | Pen      | 10     |
    | Pencil   | 5      |
    | Eraser   | 3      |



Configuration:
+++++++++++++++

* Output Column Name: RowID
* Starting Value: 1
* Data Type: String
* Size: 4
* Column Position: first


Output:
+++++++++++++++

::

    | RowID | Product | Price |
    |--------|----------|--------|
    | 0001  | Pen      | 10     |
    | 0002  | Pencil   | 5      |
    | 0003  | Eraser   | 3      |


::

    ---



Example 4: Ordered Record ID Generation Within Groups
+++++++++++++++



Input:
+++++++++++++++

::

    | Dept | Salary | Name |
    |-------|---------|------|
    | HR    | 50000   | John |
    | HR    | 60000   | Mary |
    | IT    | 80000   | Alice |
    | IT    | 75000   | Bob |



Configuration:
+++++++++++++++

* Output Column Name: RankID
* Starting Value: 1
* Data Type: Int64
* Generation Scope: within_group
* Group By Columns: Dept
* Order Rows Within Each Group: Salary desc


Output:
+++++++++++++++

::

    | Dept | Salary | Name | RankID |
    |-------|---------|------|--------|
    | HR    | 60000   | Mary | 1      |
    | HR    | 50000   | John | 2      |
    | IT    | 80000   | Alice | 1     |
    | IT    | 75000   | Bob   | 2     |
