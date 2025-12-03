Pivot By Advanced
=========== 

Pivot Node with advanced options

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodePivotAdvance

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - groupingCols
        - Grouping Columns
        - Select one or more columns to group the data by. These columns will form the rows in the pivot table, categorizing the data (e.g., by Department or Region).
      * - pivotCol
        - Pivot Column
        - Choose the column whose unique values will be turned into new columns in the pivot table (e.g., Location, creating columns like 'New York' and 'New Jersey'). This is required for pivoting.
      * - uniqueValues
        - Unique Values
        - Enter a comma-separated list of unique values expected in the Pivot Column (e.g., 'New York,New Jersey'). This is optional but recommended for better performance, as it avoids the need for Spark to calculate distinct values automatically.
      * - aggregateCol
        - Aggregate Column
        - Select the column to perform aggregations on (e.g., Salary for summing totals, or Names for concatenating lists). This column provides the values that will be summarized in the pivot table cells.
      * - aggregateOperations
        - Aggregate Operation to use
        - Choose one or more aggregation functions to apply to the Aggregate Column. Options include sum (total), avg (average), min, max, count (non-null), count_distinct (unique non-null), concat (join strings), first, last, count_with_nulls (all rows), count_distinct_with_nulls (unique including nulls), percent_row (% of row), percent_col (% of column), total_row (add total row), total_col (add total column).
      * - options
        - Options
        - 
      * - caseInsensitive
        - Case Insensitive Grouping
        - Enable this to make grouping case-insensitive (e.g., 'New York' and 'new york' treated as the same). Default is false, meaning case-sensitive grouping.
      * - retainSpecialChars
        - Retain Special Characters
        - If set to true, keep special characters (like #, *, spaces) in the new column names created from pivot values. If false (default), replace them with underscores for cleaner, compatible column names.
      * - concatSeparator
        - Concatenation Separator
        - Specify the separator to use when concatenating strings with the 'concat' operation (e.g., ',' or '; '). Only applies if 'concat' is selected in Aggregate Operations. Default is ','.
      * - maxConcatLength
        - Field Size (Max Characters)
        - Set the maximum number of characters for concatenated strings. If the result exceeds this length, it will be truncated, and a warning will be logged. Default is 2048.
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Specify the names for the output columns. If left empty, names will be inferred automatically from the pivot operation.
      * - outputColTypes
        - Column Types of the Table
        - Define the data types for the output columns (e.g., String, Integer). If not provided, types will be inferred.
      * - outputColFormats
        - Column Formats
        - Set custom formats for the output columns (e.g., date formats like 'yyyy-MM-dd'). Optional; used for formatting display or output.


Details
-------
Pivot By Advance Node Details
---------------


The Pivot By Advance node transforms an incoming DataFrame into a powerful pivot table (crosstab) by grouping rows, pivoting on a column's unique values, and applying one or more aggregation functions. Ideal for business reporting, dashboards, and summary analytics.



Core Parameters
+++++++++++++++



Grouping Columns
+++++++++++++++


* Select one or more columns that define the rows of the pivot table (e.g., Department, Region, Year).
* These act as categories for grouping the data.


Pivot Column
+++++++++++++++

* Required for standard pivoting.
* The column whose distinct values will become new columns in the output (e.g., Location → columns "New York", "New Jersey").


Unique Values (Optional)
+++++++++++++++

* Comma-separated list of expected values in the Pivot Column (e.g., New York,New Jersey).
* Providing this significantly improves performance by skipping Spark's internal distinct computation.


Aggregate Column
+++++++++++++++

* The column containing values to aggregate (e.g., Salary, Revenue, CustomerName).


Aggregate Operations
+++++++++++++++

* Choose one or multiple functions:
* sum, avg, min, max
* count (non-null), count_distinct (unique non-null)
* first, last
* count_with_nulls (counts every row), count_distinct_with_nulls (treats null as a distinct value)
* concat (joins strings)
* percent_row (% of row total), percent_col (% of column total)
* total_row (adds a "Total" row at the bottom)
* total_col (adds a "Total" column on the right)


Options Tab
+++++++++++++++



Case Insensitive Grouping
+++++++++++++++

* When enabled, treats "New York" and "new york" as the same group.


Retain Special Characters
+++++++++++++++

* If disabled (default), replaces spaces, #, *, etc., with underscores in generated column names.
* If enabled, keeps original characters (useful for readability, but may cause issues in some downstream tools).


Concatenation Separator
+++++++++++++++

* Only used with concat operation (default: comma).


Field Size (Max Characters)
+++++++++++++++

* Maximum length for concatenated strings. Longer results are truncated with a warning in logs (default: 2048).


InferSchema Tab
+++++++++++++++



Output Column Names / Types / Formats
+++++++++++++++

* Optionally define the exact output schema.
* If left empty, schema is automatically inferred from the result.


Special Behaviors
+++++++++++++++


* If percent_row or percent_col is selected without sum, sum is automatically added temporarily for calculation.
* If only total_row / total_col is used without a pivot column, the node computes grouped totals only.
* Column names are cleaned (special chars → _) unless Retain Special Characters is enabled.


Examples
-------
Pivot By Advance Node Examples
---------------



Example 1 – Basic Pivot (Sum)
+++++++++++++++



Incoming Data
+++++++++++++++

::

    | EMP_CD | EMP_NAME | LOCATION   | DEPT      | SALARY |
    |--------|----------|------------|-----------|--------|
    | E01    | DAVID    | NEW YORK   | HR        | 10000  |
    | E02    | JOHN     | NEW JERSEY | SALES     | 11000  |
    | E03    | MARTIN   | NEW YORK   | MARKETING | 12000  |
    | E04    | TONY     | NEW JERSEY | MARKETING | 13000  |



Configuration
+++++++++++++++


* Grouping Columns: DEPT
* Pivot Column: LOCATION
* Aggregate Column: SALARY
* Aggregate Operations: sum


Result
+++++++++++++++

::

    | DEPT      | NEW_JERSEY | NEW_YORK   |
    |-----------|------------|----------|
    | HR        | null       | 10000    |
    | SALES     | 11000      | null     |
    | MARKETING | 13000      | 12000    |



Example 2 – Group Totals Only (No Pivot)
+++++++++++++++



Configuration
+++++++++++++++

* Grouping Columns: DEPT
* Pivot Column: (empty)
* Aggregate Column: SALARY
* Aggregate Operations: total_col


Result
+++++++++++++++

::

    | DEPT      | Total  |
    |-----------|--------|
    | HR        | 10000  |
    | SALES     | 11000  |
    | MARKETING | 25000  |



Example 3 – Concatenation of Names
+++++++++++++++



Configuration
+++++++++++++++

* Grouping Columns: DEPT
* Pivot Column: LOCATION
* Aggregate Column: EMP_NAME
* Aggregate Operations: concat
* Concat Separator: "; "


Result
+++++++++++++++

::

    | DEPT      | NEW_JERSEY | NEW_YORK |
    |-----------|------------|----------|
    | HR        | null       | DAVID    |
    | SALES     | JOHN       | null     |
    | MARKETING | TONY       | MARTIN   |



Example 4 – Full Featured (Multiple Aggs + Totals + Percentages)
+++++++++++++++



Incoming Data (expanded)
+++++++++++++++

::

    | EMP_CD | EMP_NAME | LOCATION   | DEPT      | SALARY |
    |--------|----------|------------|-----------|--------|
    | E01    | DAVID    | NEW YORK   | HR        | 10000  |
    | E06    | LISA     | NEW JERSEY | HR        | 15000  |
    | E02    | JOHN     | NEW JERSEY | SALES     | 11000  |
    | E05    | ROSS     | NEW YORK   | SALES     | 14000  |
    | E03    | MARTIN   | NEW YORK   | MARKETING | 12000  |
    | E04    | TONY     | NEW JERSEY | MARKETING | 13000  |



Configuration
+++++++++++++++

* Grouping Columns: DEPT
* Pivot Column: LOCATION
* Unique Values: NEW YORK,NEW JERSEY
* Aggregate Column: SALARY
* Aggregate Operations: sum, count, percent_row, percent_col, total_row, total_col


Result (simplified view)
+++++++++++++++

::

    | DEPT      | Sum_NEW_JERSEY | Sum_NEW_YORK | Count_NEW_JERSEY | Count_NEW_YORK | Total_Sum | XRow_NEW_JERSEY | XRow_NEW_YORK | XCol_NEW_JERSEY | XCol_NEW_YORK |
    |-----------|----------------|--------------|------------------|----------------|-----------|-----------------|---------------|-----------------|---------------|
    | HR        | 15000         |10000        |1                |1              |25000     |60.0            |40.0          |32.61           |25.0          |
    | SALES     |11000          |14000        |1                |1              |25000     |44.0            |56.0          |23.91           |35.0          |
    | MARKETING |13000          |12000        |1                |1              |25000     |52.0            |48.0          |28.26           |30.0          |
    | Total     |46000          |40000        |3                |3              |86000     |53.49           |46.51         |100.0           |100.0         |



Example 5 – Handling Nulls & Distinct Counts
+++++++++++++++



Configuration
+++++++++++++++

* Grouping Columns: CATEGORY
* Pivot Column: TYPE
* Aggregate Column: VALUE
* Aggregate Operations: count_with_nulls, count_distinct_with_nulls


Result
+++++++++++++++

::

    | CATEGORY | count_distinct_with_nulls_X | count_distinct_with_nulls_Y | count_with_nulls_X | count_with_nulls_Y |
    |----------|-----------------------------|-----------------------------|--------------------|-------------------|
    | A        | 2                           | 1                           | 2                  | 1                 |
    | B        | 1                           | 1                           | 1                  | 1                 |



Example 6 – Concat with Truncation & Special Chars
+++++++++++++++



Configuration
+++++++++++++++

* Grouping Columns: GROUP
* Pivot Column: SUBGROUP
* Aggregate Column: DESCRIPTION
* Aggregate Operations: concat

::

    - Concat Separator: " | "

* Max Concat Length: 20
* Retain Special Characters: false


Result
+++++++++++++++

::

    | GROUP | Concat_High_1                | Concat_Low_2 |
    |-------|-------------------------------------|--------------|
    | P     | Item one, very long des...         | null         |
    | Q     | null                                | Short        |
