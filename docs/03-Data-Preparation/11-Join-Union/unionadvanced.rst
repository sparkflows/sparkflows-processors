Union Advanced
===========

Smart Union node that combines multiple DataFrames with full control: union by column name or position, include all columns or only common ones, and automatically handle mismatched schemas with null padding. Perfect for merging monthly files, combining sources with evolving schemas, and building robust incremental pipelines.

Input
--------------
It accepts two or more DataFrames as input from the previous nodes.

Output
--------------
This node outputs a single DataFrame resulting from the union operation based on the selected configuration.

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeUnionAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - allowMissingColumns
        - Allow Missing Columns
        - When true → DataFrames with different schemas are automatically aligned by filling missing columns with null values. When false → all input DataFrames must have exactly the same schema (fails otherwise). Recommended: true for real-world incremental loads.
      * - configBy
        - Configure By
        - How columns are matched across DataFrames: • NAME → matches by column name (case-sensitive). Safest and most common choice. • POSITION → matches by column order (1st column of each DF lines up, 2nd column, etc.). Uses the column names from the first incoming DataFrame.
      * - outputFields
        - Output Fields
        - Which columns appear in the final result: • ALL → includes every column that exists in any input (missing values become null). Best for full history and audit. • COMMON → keeps only columns that exist in ALL inputs. Great when you want a clean, consistent schema.


Details
-------
Union Advanced Node – The Smart Way to Combine Data
+++++++++++++++


The Union Advanced node is the most flexible and production-ready way to stack DataFrames vertically. Whether you're appending daily files, merging regional exports, or combining sources that evolve over time — this node handles it gracefully without breaking your pipeline.



Real-World Use Cases
+++++++++++++++


* Monthly/weekly/daily incremental loads (new columns appear over time)
* Combining sales data from different regions/countries with slightly different schemas
* Merging legacy and new systems during migration
* Building historical tables where schema evolves naturally
* Preparing data for slowly changing dimensions (SCD)


Key Advantages Over Basic Union
+++++++++++++++

* Automatically handles missing or extra columns
* Two matching strategies (by name or position)
* Option to keep full history (ALL) or enforce strict schema (COMMON)
* No manual column alignment needed
* Works seamlessly with 2 to 100+ input branches


Best Practices
+++++++++++++++

* Always use configBy = NAME (unless you have a very specific positional reason)
* Use outputFields = ALL + allowMissingColumns = true for audit-ready, future-proof pipelines
* Use outputFields = COMMON when downstream models or reports require fixed schema


Examples
-------
Union Advanced – Practical Business Examples
+++++++++++++++



Example 1 – Monthly Sales Files (Schema Evolves Over Time)
+++++++++++++++



Scenario
+++++++++++++++

Jan file has columns: date, customer_id, amount

Feb file adds new column: promo_code

Mar file adds: channel



Configuration
+++++++++++++++


* Allow Missing Columns: true
* Configure By: NAME
* Output Fields: ALL


Result
+++++++++++++++

::

    | date       | customer_id | amount | promo_code | channel |
    |------------|-------------|--------|------------|---------|
    | 2025-01-01 | 101         | 150    | null       | null    |
    | ...        | ...         | ...    | ...        | ...     |
    | 2025-02-01 | 205         | 320    | SUMMER10   | null    |
    | 2025-03-01 | 310         | 450    | SPRING25   | Online  |



Perfect for building a full historical sales table.



Example 2 – Regional Reports (Different Column Order & Extra Columns)
+++++++++++++++



US Report: customer_id, name, state, revenue
+++++++++++++++



EU Report: revenue, customer_name, country, customer_id
+++++++++++++++



APAC Report: customer_id, revenue, region
+++++++++++++++



Configuration
+++++++++++++++


* Allow Missing Columns: true
* Configure By: NAME
* Output Fields: ALL


Result
+++++++++++++++


All regions stacked with consistent column order by name, missing fields filled with null.



Example 3 – Enforce Strict Schema (Data Quality Gate)
+++++++++++++++



You only want columns that exist in every single daily file
+++++++++++++++



Configuration
+++++++++++++++


* Allow Missing Columns: true
* Configure By: NAME
* Output Fields: COMMON


Result
+++++++++++++++


Only columns present in 100% of inputs are kept — acts as automatic schema validation.



Example 4 – Legacy Positional Files (Old Systems)
+++++++++++++++



Old COBOL extracts have fixed positions, no headers, columns always in same order
+++++++++++++++



Configuration
+++++++++++++++


* Allow Missing Columns: false
* Configure By: POSITION
* Output Fields: ALL


Result
+++++++++++++++


Columns aligned purely by position using the schema from the first input.



Example 5 – Combining 12 Monthly Branches into Yearly Table
+++++++++++++++



12 separate pipelines (one per month) → all connect to one Union Advanced
+++++++++++++++



Configuration
+++++++++++++++


* Allow Missing Columns: true
* Configure By: NAME
* Output Fields: ALL


Result
+++++++++++++++


One clean yearly DataFrame with evolving schema preserved over time.
