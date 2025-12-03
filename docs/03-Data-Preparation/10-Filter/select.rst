Select
=========== 

The ultimate column selector – pick, rename, cast, drop, and propagate columns with pixel-perfect control. Perfect for cleaning messy inputs, preparing clean datasets for BI tools, models, or downstream pipelines, and enforcing consistent schemas.

Input
--------------
It takes a DataFrame as input.

Output
--------------
DataFrame with selected, renamed, and optionally type-cast columns.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeSelect

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - General
        - General
        - 
      * - inputCols
        - Columns
        - Columns you explicitly want to keep in the output. Drag to reorder – the order here becomes the final column order (super useful for reports!).
      * - renameCols
        - Rename
        - New names for the selected columns. Leave blank to keep original name. Example: old_name → CustomerID, AmountUSD → Revenue.
      * - colType
        - Change Data Type
        - Force cast each selected column to the correct type. Critical for fixing string → date, string → integer issues from CSV/Excel sources.
      * - drop
        - Drop & Options
        - 
      * - dropInputCols
        - Drop Columns
        - Columns you want to completely remove from the output. Great for PII, internal IDs, or junk fields.
      * - inputColumnPropagation
        - Enable Input Column Propagation
        - When true → all columns NOT listed in 'Columns' and NOT in 'Drop Columns' are automatically passed through. Perfect when you only want to rename/cast a few columns and keep everything else untouched.


Details
-------
Select Node – Your DataFrame Column Superpower
---------------


The Select node is the most frequently used transform in real-world pipelines. It does everything you expect from a modern “Select / Rename / Cast / Drop” tool — with drag-and-drop ordering, smart propagation, and zero surprises.



Why You’ll Use It Every Day
+++++++++++++++


* Clean up messy source files (CSV, Excel, JSON)
* Enforce consistent column names & types across environments
* Prepare perfect datasets for Tableau, Power BI, Looker
* Remove PII before sharing or writing to data lakes
* Reorder columns exactly how business wants them in reports
* Fix common ingestion issues (dates stored as string, numbers as string)


Key Advantages
+++++++++++++++

* Visual drag-and-drop column ordering
* One-click rename + type cast
* Smart propagation (only touch what you need to change)
* Explicit drop list for sensitive columns
* Works exactly like Alteryx / dbt / Tableau Prep — but at Spark scale


Pro Tips
+++++++++++++++

* Always turn ON “Enable Input Column Propagation” when you only need to fix a few columns
* Use it right after Read nodes to standardize incoming data
* Combine with Schema Enforcement downstream for bulletproof pipelines


Examples
-------
Select Node – Real-World Business Examples
---------------



Example 1 – Clean Raw CSV for Reporting
+++++++++++++++



Raw Input (messy)
+++++++++++++++

::

    | customer_id_str | full_name         | order_total_str | order_date_str | junk_col | _c5 |
    |-----------------|-------------------|-----------------|----------------|----------|-----|
    | 1001            | John Doe          | 1250.50         | 2025-01-15     | temp     | xyz |



Configuration
+++++++++++++++


* Columns: customer_id_str, full_name, order_total_str, order_date_str
* Rename: CustomerID, CustomerName, Revenue, OrderDate
* Change Data Type: INTEGER, STRING, DOUBLE, DATE
* Drop Columns: junk_col, _c5
* Enable Input Column Propagation: false


Clean Output
+++++++++++++++

::

    | CustomerID | CustomerName | Revenue | OrderDate  |
    |------------|--------------|---------|------------|
    | 1001       | John Doe     | 1250.50 | 2025-01-15 |



Example 2 – Only Fix a Few Columns, Keep the Rest
+++++++++++++++



You have 200 columns, but only need to rename 3 and cast 2 dates
+++++++++++++++



Configuration
+++++++++++++++

* Columns: legacy_id, transaction_date_str, close_date_str
* Rename: CustomerID, TransactionDate, CloseDate
* Change Data Type: STRING, DATE, DATE
* Enable Input Column Propagation: true
* Drop Columns: temp_flag, debug_info


Result
+++++++++++++++


All 197 untouched columns pass through automatically + your 3 fixed ones.



Example 3 – Prepare Perfect Tableau Extract
+++++++++++++++



Goal: Exact column order & names expected by dashboard
+++++++++++++++



Configuration
+++++++++++++++


* Columns: Region, Country, ProductLine, Revenue, Profit, OrderDate, CustomerSegment
* Rename: (already perfect names)
* Change Data Type: STRING, STRING, STRING, DOUBLE, DOUBLE, DATE, STRING
* Enable Input Column Propagation: false
* Drag to exact order required by viz


Result
+++++++++++++++


Tableau connects instantly — no prep needed.



Example 4 – Remove PII Before Sharing
+++++++++++++++



Configuration
+++++++++++++++


* Enable Input Column Propagation: true
* Drop Columns: SSN, FullName, Email, Phone, Address, CreditCard


Result
+++++++++++++++


All sensitive fields stripped, everything else preserved.



Example 5 – Reorder Columns for Excel Export
+++++++++++++++



Business wants: Customer Name first, then ID, then everything else
+++++++++++++++



Configuration
+++++++++++++++


* Columns: CustomerName, CustomerID → place at top
* Enable Input Column Propagation: true


Result
+++++++++++++++


Excel opens with the two key columns first — exactly as requested.
