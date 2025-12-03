Expressions
===========

The most powerful and intuitive column calculator – add unlimited new columns using full Spark SQL expressions. Perfect for feature engineering, business logic, cleaning, formatting, date manipulation, and creating report-ready fields without writing code.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeExpressions

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Expressions
        - Expressions
        - 
      * - outputCols
        - Column Name
        - Name of the new column you want to create (e.g., Revenue_Net, FullName, IsHighValue, OrderMonth).
      * - expressions
        - Expression
        - Full Spark SQL expression to compute the column value. Supports 400+ functions: math, string, date, conditional, regex, JSON, arrays, etc. Quick Examples: • amount * quantity • concat(first_name, ' ', last_name) • date_format(order_date, 'yyyy-MM') • when(amount > 10000, 'VIP').otherwise('Regular') • coalesce(email, phone, 'unknown')
      * - propagation
        - ColumnPropagation
        - 
      * - inputColumnPropagation
        - Input Column Propagation
        - When true (default) → all original columns are automatically kept + your new ones. Set to false if you want only the newly created columns.
      * - outputSchema
        - InferSchema
        - 
      * - outputColNames
        - Output Column Name
        - Force exact output column names (useful with propagation = false)
      * - outputColTypes
        - Output Column Type
        - Force data types for new columns
      * - outputColFormats
        - Output Column Format
        - Display formats (dates, numbers)


Details
-------
Expressions Node – Your No-Code Business Logic Powerhouse
+++++++++++++++


The Expressions node is the #1 most-used transform in production pipelines. It replaces dozens of individual nodes (String Ops, Date Ops, Math, If-Then-Else) with one clean, fast, and readable interface using standard Spark SQL syntax.



Why Teams Love It
+++++++++++++++


* Full Spark SQL → 400+ functions, no black boxes
* Instant preview of results
* Auto-complete & syntax highlighting
* Perfect for KPIs, cleansing, segmentation, formatting
* Same syntax works in dbt, Snowflake, BigQuery, Databricks


Most Popular Real-World Use Cases
+++++++++++++++

* Revenue calculations (net, gross, margin %)
* Customer segmentation (VIP, Churn Risk, RFM)
* Name/address standardization
* Date bucketing (Month, Quarter, FY, Age bands)
* Flags & indicators (IsNewCustomer, HasEmail)
* Safe division (nullif, coalesce)
* JSON extraction, regex cleaning


Pro Tips
+++++++++++++++

* Use `when(...).otherwise(...)` instead of nested ifs
* Wrap divisions in `coalesce(..., 0)` or `nullif(denominator, 0)`
* Always test with `limit 10` first
* Combine with Schema tab to force exact types


Examples
-------
Expressions Node – Real Business Examples
+++++++++++++++



Example 1 – Revenue & Margin Calculations
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | gross_revenue     | amount * quantity                               |
    | discount_amt      | gross_revenue * coalesce(discount_rate, 0)      |
    | net_revenue       | gross_revenue - discount_amt                    |
    | margin_pct        | round((net_revenue - cost) / net_revenue * 100, 2) |



Example 2 – Customer Name & Segmentation
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | full_name         | concat_ws(' ', initcap(first_name), initcap(last_name)) |
    | name_clean        | regexp_replace(trim(full_name), '\\s+', ' ')    |
    | customer_tier     | when(net_revenue >= 100000, 'Platinum').when(net_revenue >= 50000, 'Gold').when(net_revenue >= 10000, 'Silver').otherwise('Bronze') |



Example 3 – Date Intelligence
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | order_month       | date_format(order_date, 'yyyy-MM')              |
    | order_quarter     | concat('Q', quarter(order_date))                |
    | days_since_order  | datediff(current_date(), order_date)            |
    | is_recent         | days_since_order <= 30                          |
    | fiscal_year       | when(month(order_date) >= 4, year(order_date) + 1).otherwise(year(order_date)) |



Example 4 – Safe Math & Cleaning
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | avg_basket_size   | round(amount / nullif(items_count, 0), 2)       |
    | email_domain      | substring_index(email, '@', -1)                 |
    | phone_clean       | regexp_replace(phone, '[^0-9]', '')             |
    | revenue_safe      | coalesce(revenue, 0)                            |



Example 5 – Flags & Indicators
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | has_email         | email is not null                               |
    | is_new_customer   | first_order_date = order_date                   |
    | high_value_flag   | amount > 5000                                   |
    | status            | when(is_cancelled, 'Cancelled').when(is_shipped, 'Shipped').otherwise('Processing') |



Example 6 – Current Timestamp & Audit Columns
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | load_date         | current_date()                                  |
    | load_timestamp    | current_timestamp()                             |
    | run_id            | 'RUN_' || date_format(current_timestamp(), 'yyyyMMdd_HHmmss') |



Example 7 – Complex JSON & Array Handling
+++++++++++++++

::

    | Output Column     | Expression                                      |
    |-------------------|-------------------------------------------------|
    | event_type        | json_tuple(events_json, 'type')[0]              |
    | tags_array        | split(tags_string, ',')                         |
    | tag_count         | size(tags_array)                                |
    | has_tag_promo     | array_contains(tags_array, 'PROMO')             |
