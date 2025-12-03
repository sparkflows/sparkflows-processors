Sort By
=========== 

Sorts the entire DataFrame by one or multiple columns with full control over ascending/descending order per column. Essential for ranked reports, leaderboards, time-series ordering, and preparing data for window functions or exports.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeSortBy

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - sortByColNames
        - Columns
        - Select one or more columns to sort by. Drag to reorder — the top column is the primary sort key, followed by secondary, tertiary, etc.
      * - ascDesc
        - Sorting Order
        - Individually set ASC (ascending) or DESC (descending) for each selected column. Example: Salary → DESC, then Department → ASC, then Name → ASC


Details
-------
Sort By Node – Full Control Over Data Ordering
---------------


The Sort By node gives you pixel-perfect control over row order in your DataFrame. Whether you need top-10 customers by revenue, chronological transaction history, or complex multi-level ranking (e.g., Country DESC → Revenue DESC → Customer Name ASC), this node handles it cleanly and efficiently.



Perfect For
+++++++++++++++


* Leaderboards and rankings
* Monthly/quarterly reports that must show highest → lowest
* Time-series data (sort by date descending for latest first)
* Preparing data before window functions (rank(), row_number(), etc.)
* Excel/CSV exports where business expects specific order
* Top-N + Others grouping (sort first, then add row number, then filter)


Key Features
+++++++++++++++

* Multi-level sorting (up to as many columns as needed)
* Independent ASC/DESC per column
* Drag-and-drop reordering of sort priority
* Works on strings, numbers, dates, timestamps, nulls (nulls last by default)
* Fully distributed — works on billions of rows


Pro Tips
+++++++++++++++

* Always place Sort By before Limit if creating “Top 100” reports
* For stable sorting across runs, include a unique ID as the last sort column (ASC)
* Nulls are treated as “greater than” any value in ASC order and “smaller than” in DESC order


Examples
-------
Sort By Node – Real Business Examples
---------------



Example 1 – Top Earners Report (Classic Use Case)
+++++++++++++++



Goal: Show employees from highest to lowest salary, then by name alphabetically if tie
+++++++++++++++



Configuration
+++++++++++++++


* Columns: SALARY, EMP_NAME
* Order: DESC, ASC

Result
+++++++++++++++

::

    | EMP_CD | EMP_NAME | SALARY       |
    |--------|----------|--------------|
    | C04    | MARCUS   | AUD 350000.00|
    | C01    | MATT     | USD 200000.00|
    | C02    | LISA     | GBP 100000.00|
    | C03    | ROBIN    | EUR 15000.00 |



Example 2 – Latest Transactions First (Most Recent on Top)
+++++++++++++++



Configuration
+++++++++++++++

* Columns: TRANSACTION_DATE, TRANSACTION_ID
* Order: DESC, DESC

Result
+++++++++++++++


Latest transactions appear at the top — perfect for monitoring dashboards.



Example 3 – Multi-Level Sales Ranking
+++++++++++++++



Goal: Rank by Region (A-Z), then by Revenue (high→low), then by Customer Name (A-Z)
+++++++++++++++



Configuration
+++++++++++++++


* Columns: REGION, TOTAL_REVENUE, CUSTOMER_NAME
* Order: ASC, DESC, ASC

Result
+++++++++++++++


Clean, readable regional sales report exactly as business expects.



Example 4 – Prepare for Top-10 + Others
+++++++++++++++



Step 1: Sort By → REVENUE (DESC)
+++++++++++++++



Step 2: Add Row Number column
+++++++++++++++



Step 3: Use Expression or Filter: case when row_num <= 10 then CUSTOMER else 'Others' end
+++++++++++++++



Result
+++++++++++++++

Top 10 customers shown individually, rest grouped as “Others”.



Example 5 – Alphabetical Customer List with Null Handling
+++++++++++++++



Data has some missing LAST_NAME
+++++++++++++++



Configuration
+++++++++++++++


* Columns: LAST_NAME, FIRST_NAME
* Order: ASC, ASC

Result
+++++++++++++++


Rows with null LAST_NAME appear at the bottom (Spark default behavior).



Example 6 – Stable Sorting Across Multiple Runs
+++++++++++++++



Configuration
+++++++++++++++


* Columns: SCORE, CUSTOMER_ID
* Order: DESC, ASC

Result
+++++++++++++++


Even when scores are tied, same customer always appears in same position because of unique ID tie-breaker.
