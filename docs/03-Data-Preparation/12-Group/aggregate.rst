Aggregate
===========

The most powerful and flexible aggregation node – combines Group By, multiple aggregations, Pivot, conditional expressions, and column propagation in one easy-to-use interface. Perfect for business reporting, dashboards, KPIs, and analytics summaries.

Input
--------------
Accepts one or more DataFrames as input.

Output
--------------
Returns an aggregated DataFrame.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeAggregateColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Aggregate
        - Aggregate Columns
        - 
      * - aggregatetargetColumns
        - Target Column
        - Name of the new column that will hold the aggregated result (e.g., total_sales, order_count, avg_price). This is the column name users will see in reports.
      * - aggregateexpressions
        - Expression
        - Spark SQL aggregation expression. Examples: • sum(amount) • count(*) • avg(price) • max(date) • min(temperature) • count(distinct customer_id) • sum(amount * quantity) • stddev(pop) • corr(price, volume)
      * - propagateAllInputColumns
        - Propagate All Input Columns
        - When true → all non-grouped columns are automatically kept in the output using first() (or last() if you change it later). Great for keeping customer name, latest order date, etc., alongside totals.
      * - GroupBy
        - Group By Columns
        - 
      * - groupByTargetColumns
        - Target Column
        - Output column name for the grouping key (e.g., region, department, year_month). Use this to rename or transform grouping columns (e.g., year(order_date) → order_year).
      * - groupByExpressions
        - Expression
        - How to group the data. Usually just the column name, but can be complex: • region • year(order_date) • concat(year, '-', month) • substr(postal_code, 1, 3) • date_trunc('month', order_date)
      * - Pivot
        - Pivot
        - 
      * - pivotCol
        - Pivot Column
        - Column whose distinct values become new columns (e.g., product_category, region, status). Turns long data into wide crosstab format – ideal for Excel reports and dashboards.
      * - uniqueValues
        - Unique Values
        - Comma-separated list of expected values (e.g., Electronics,Clothing,Food or Jan,Feb,Mar,Apr,...,Dec). Dramatically improves performance and guarantees column order. Leave empty to let Spark discover values (slower on big data).
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Force exact output column names. Useful when downstream systems expect fixed headers.
      * - outputColTypes
        - Column Types of the Table
        - Force column data types (Integer, Double, String, Date, etc.). Critical for correct joins and visualizations.
      * - outputColFormats
        - Column Formats
        - Date/number format strings (e.g., yyyy-MM-dd, #,##0.00). Used for display in reports.


Details
-------
Aggregate Node – The Ultimate Business Aggregation Tool
+++++++++++++++

The Aggregate node is the Swiss Army knife of summarization. It replaces multiple simple GroupBy + Pivot + Select nodes with one intuitive interface that business analysts and data engineers love.



When to Use It
+++++++++++++++


* Monthly sales by region/product (pivot + sum)
* Customer lifetime value with latest name & join date (group by + propagate)
* Dashboard KPIs (global aggregates)
* Year-over-year comparisons (group by year/month)
* Top N per category (with window functions in expressions)
* Any Excel-style crosstab report


Key Advantages
+++++++++++++++

* Full Spark SQL expression support in Group By and Aggregate
* Optional Pivot with known values → blazing fast on huge datasets
* Automatic propagation of descriptive columns (customer name, category, etc.)
* One node does what used to take 3–5 nodes
* Explicit schema control for downstream compatibility


Pro Tips
+++++++++++++++

* Always provide Unique Values in Pivot when you know them → 10x–100x faster
* Use Propagate All Input Columns = true to keep metadata without writing first() manually
* Combine with Filter node before for conditional aggregation
* Use date_trunc('month', date) or year(date) for clean time grouping


Examples
-------
Aggregate Node – Real-World Business Examples
+++++++++++++++



Example 1 – Monthly Sales Dashboard (Classic Pivot)
+++++++++++++++



Goal: Sales by Product Category and Month (wide format for Excel)
+++++++++++++++



Configuration
+++++++++++++++


* Group By → Target: month, Expression: date_trunc('month', order_date)
* Pivot Column: category
* Unique Values: Electronics,Clothing,Food,Books
* Aggregate → Target: total_sales, Expression: sum(amount)
* Propagate All Input Columns: false

Result
+++++++++++++++

::

    | month      | Electronics | Clothing | Food | Books |
    |------------|-------------|----------|------|-------|
    | 2025-01-01 | 45000       | 28000    | 12000| 8000  |
    | 2025-02-01 | 52000       | 31000    | 13500| 9200  |



Example 2 – Customer Summary with Latest Info
+++++++++++++++



Goal: Total spend per customer + latest order date & name
+++++++++++++++



Configuration
+++++++++++++++

* Group By → Target: customer_id, Expression: customer_id
* Aggregate → Target: total_spent, Expression: sum(amount)
* Aggregate → Target: order_count, Expression: count(*)
* Propagate All Input Columns: true

Result
+++++++++++++++

::

    | customer_id | total_spent | order_count | customer_name | latest_order_date |
    |-------------|-------------|-------------|---------------|-------------------|
    | 101         | 2500        | 12          | John Doe      | 2025-03-15        |
    | 102         | 1800        | 8           | Jane Smith    | 2025-03-10        |



Example 3 – Regional KPIs (No Group By = Global)
+++++++++++++++



Configuration
+++++++++++++++

* Aggregate → Target: total_revenue, Expression: sum(amount)
* Aggregate → Target: unique_customers, Expression: count(distinct customer_id)
* Aggregate → Target: avg_order_value, Expression: avg(amount)
* Propagate All Input Columns: false

Result
+++++++++++++++

::

    | total_revenue | unique_customers | avg_order_value |
    |---------------|------------------|-----------------|
    | 1,250,000     | 8,421            | 148.32          |



Example 4 – Year-over-Year Growth by Category
+++++++++++++++



Configuration
+++++++++++++++

* Group By → Target: year, Expression: year(order_date)
* Group By → Target: category, Expression: category
* Aggregate → Target: sales, Expression: sum(amount)
* Propagate All Input Columns: false

Result (ready for % change calculation downstream)
+++++++++++++++

::

    | year | category     | sales     |
    |------|--------------|-----------|
    | 2024 | Electronics  | 420000    |
    | 2025 | Electronics  | 580000    |
    | 2024 | Clothing     | 310000    |
    | 2025 | Clothing     | 410000    |



Example 5 – Top 3 Products per Region (using window functions)
+++++++++++++++



Configuration
+++++++++++++++

* Group By → Target: region, Expression: region
* Aggregate → Target: product_sales, Expression: sum(amount)
* Aggregate → Target: rank_in_region, Expression: rank() over (partition by region order by sum(amount) desc)
* Then add a Filter node after: rank_in_region <= 3

Result
+++++++++++++++


Only the top 3 products per region appear.



Example 6 – Distinct Combinations Only (no aggregation)
+++++++++++++++



Goal: List of unique Country + Channel combinations
+++++++++++++++



Configuration
+++++++++++++++


* Group By → Target: country, Expression: country
* Group By → Target: channel, Expression: channel
* No Aggregate columns
* Propagate All Input Columns: false

Result
+++++++++++++++

::

    | country     | channel   |
    |-------------|-----------|
    | USA         | Online    |
    | USA         | Retail    |
    | Germany     | Online    |
    | France      | Retail    |
