Join Advanced
=========== 

Append fields from a Source DataFrame to every row of a Target DataFrame (Cartesian-style append).

Type
--------- 

join2inputs

Class
--------- 

fire.nodes.etl.NodeJoin

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Join
        - Join
        - 
      * - joinBy
        - Join By
        - whether to append dataframe as a table to email content
      * - leftTableJoinColumn
        - LeftTableJoinColumn
        - 
      * - rightTableJoinColumn
        - RightTableJoinColumn
        - 
      * - Select
        - Select
        - 
      * - selectLeftFields
        - Select Left Fields
        - Columns
      * - dataTypeLeftFields
        - Data Type Left Fields
        - New data type (INTEGER, DOUBLE, STRING, LONG, SHORT)
      * - renameLeftFields
        - Rename Left Fields
        - rename column
      * - selectRightFields
        - Select Right Fields
        - Columns
      * - dataTypeRightFields
        - Data Type Right Fields
        - New data type (INTEGER, DOUBLE, STRING, LONG, SHORT)
      * - renameRightFields
        - Rename Right Fields
        - rename column
      * - Drop
        - Drop
        - 
      * - inputPropagateSchema
        - Propagate Input Schema
        - propagate input schema
      * - dropLeftFields
        - Drop Left Columns
        - Drop Columns
      * - dropRightFields
        - Drop Right Columns
        - Drop Columns


Details
===============
Join Node Details
---------------


This node performs comprehensive join operations between two DataFrames, supporting both position-based and field-based joins with extensive data transformation capabilities. It enables inner joins with anti-join outputs to identify unmatched records for complete data analysis.


The configuration includes:


* **Join Tab**: Selection of join type (Position or Specific Fields) and specification of join keys when using field-based joins
* **Select Tab**: Independent column selection, renaming, and data type casting for both left and right input DataFrames
* **Drop Tab**: Column dropping configuration with schema propagation options


Key features:


* **Dual Output Strategy**: Produces inner join results plus left/right anti-joins for unmatched record analysis
* **Conflict Resolution**: Automatically handles column name conflicts by prefixing right-side columns
* **Data Transformation**: Supports column selection, renaming, type casting, and dropping in a single operation
* **Null Handling**: Robust normalization of null and empty values for reliable join matching
* **Schema Management**: Maintains original schemas for anti-join outputs while applying transformations to inner join results


Examples
===============
Join Node Examples
---------------


::

    ---



:Example 1 — Basic Customer-Order Join with Unmatched Analysis
+++++++++++++++



* *Left DataFrame: Customers**

::

    customer_id | name   | city
    ------------|--------|---------
    1          | John   | NYC
    2          | Alice  | LA
    3          | Bob    | Chicago
    4          | Eva    | Miami



* *Right DataFrame: Orders**

::

    order_id | customer_id | amount  | order_date
    ---------|-------------|---------|------------
    101      | 1           | 100.50  | 2023-01-15
    102      | 1           | 200.00  | 2023-02-20
    103      | 2           | 150.75  | 2023-01-10
    104      | 4           | 300.25  | 2023-03-05



* *Configuration**
* **Join By:** Specific Fields
* **Left Table Join Column:** customer_id
* **Right Table Join Column:** customer_id
* **Select Left Fields:** [customer_id, name, city]
* **Select Right Fields:** [order_id, amount, order_date]

* *Inner Join Output**

::

    customer_id | name   | city    | order_id | amount  | order_date
    ------------|--------|---------|----------|---------|------------
    1          | John   | NYC     | 101      | 100.50  | 2023-01-15
    1          | John   | NYC     | 102      | 200.00  | 2023-02-20
    2          | Alice  | LA      | 103      | 150.75  | 2023-01-10
    4          | Eva    | Miami   | 104      | 300.25  | 2023-03-05



* *Left Anti-Join Output (Customers without orders)**

::

    customer_id | name   | city
    ------------|--------|---------
    3          | Bob    | Chicago



::

    ---



:Example 2 — Department-Employee Join with Column Renaming
+++++++++++++++


* *Left DataFrame: Departments**

::

    dept_id | dept_name    | location | budget
    --------|--------------|----------|--------
    D1      | Sales        | North    | 500000
    D2      | Engineering  | South    | 800000
    D3      | Marketing    | East     | 400000



* *Right DataFrame: Employees**

::

    emp_id | name  | department_id | salary | hire_date
    -------|-------|---------------|--------|------------
    E1     | Sarah | D1            | 75000  | 2020-05-15
    E2     | Mike  | D1            | 80000  | 2019-08-20
    E3     | Lisa  | D2            | 95000  | 2021-01-10
    E4     | Tom   | D4            | 70000  | 2022-03-01



* *Configuration**
* **Join By:** Specific Fields
* **Left Table Join Column:** dept_id
* **Right Table Join Column:** department_id
* **Select Left Fields:** [dept_id, dept_name, location]
* **Rename Left Fields:** [dept_id, dept_name, dept_location]
* **Select Right Fields:** [emp_id, name, salary]
* **Rename Right Fields:** [employee_id, employee_name, annual_salary]
* **Drop Left Fields:** [budget]
* **Drop Right Fields:** [hire_date]

* *Inner Join Output**

::

    dept_id | dept_name   | dept_location | employee_id | employee_name | annual_salary
    --------|-------------|---------------|-------------|---------------|--------------
    D1      | Sales       | North         | E1          | Sarah         | 75000
    D1      | Sales       | North         | E2          | Mike          | 80000
    D2      | Engineering | South         | E3          | Lisa          | 95000



* *Left Anti-Join Output (Departments without employees)**

::

    dept_id | dept_name | location | budget
    --------|-----------|----------|--------
    D3      | Marketing | East     | 400000



* *Right Anti-Join Output (Employees without departments)**

::

    emp_id | name | department_id | salary | hire_date
    -------|------|---------------|--------|------------
    E4     | Tom  | D4            | 70000  | 2022-03-01



::

    ---



:Example 3 — Product Inventory Join with Data Type Casting
+++++++++++++++


* *Left DataFrame: Products**

::

    product_code | product_name | category     | price_string
    -------------|--------------|-------------|-------------
    P100         | Laptop       | Electronics | "999.99"
    P200         | Chair        | Furniture   | "149.50"
    P300         | Monitor      | Electronics | "299.00"
    P400         | Desk         | Furniture   | "450.00"



* *Right DataFrame: Inventory**

::

    item_id | product_code | quantity | last_updated
    --------|-------------|----------|-------------
    I1      | P100        | 25       | 2023-04-01
    I2      | P200        | 40       | 2023-04-02
    I3      | P300        | 15       | 2023-04-01
    I5      | P500        | 10       | 2023-04-03



* *Configuration**
* **Join By:** Specific Fields
* **Left Table Join Column:** product_code
* **Right Table Join Column:** product_code
* **Select Left Fields:** [product_code, product_name, category, price_string]
* **DataType Left Fields:** [STRING, STRING, STRING, DOUBLE]
* **Select Right Fields:** [item_id, quantity, last_updated]
* **DataType Right Fields:** [STRING, INTEGER, DATE]
* **Rename Left Fields:** [prod_code, prod_name, prod_category, price]

* *Inner Join Output**

::

    prod_code | prod_name | prod_category | price  | item_id | quantity | last_updated
    ----------|-----------|---------------|--------|---------|----------|-------------
    P100      | Laptop    | Electronics   | 999.99 | I1      | 25       | 2023-04-01
    P200      | Chair     | Furniture     | 149.50 | I2      | 40       | 2023-04-02
    P300      | Monitor   | Electronics   | 299.00 | I3      | 15       | 2023-04-01



* *Left Anti-Join Output (Products without inventory)**

::

    product_code | product_name | category   | price_string
    -------------|--------------|-----------|-------------
    P400         | Desk         | Furniture | "450.00"



::

    ---



:Example 4 — Multi-Column Join with Complex Relationships
+++++++++++++++


* *Left DataFrame: Student Enrollments**

::

    student_id | course_code | semester | grade | instructor
    -----------|-------------|----------|-------|-----------
    S100       | MATH101     | Fall     | A     | Dr. Smith
    S100       | CS201       | Fall     | B     | Dr. Johnson
    S200       | MATH101     | Spring   | B+    | Dr. Smith
    S300       | PHY301      | Fall     | A-    | Dr. Brown



* *Right DataFrame: Course Catalog**

::

    course_id | course_code | semester | credits | department
    ----------|-------------|----------|---------|------------
    C1        | MATH101     | Fall     | 4       | Mathematics
    C2        | CS201       | Fall     | 3       | Computer Science
    C3        | MATH101     | Spring   | 4       | Mathematics
    C4        | BIO202      | Fall     | 4       | Biology



* *Configuration**
* **Join By:** Specific Fields
* **Left Table Join Column:** [course_code, semester]
* **Right Table Join Column:** [course_code, semester]
* **Select Left Fields:** [student_id, course_code, semester, grade]
* **Select Right Fields:** [course_id, credits, department]

* *Inner Join Output**

::

    student_id | course_code | semester | grade | course_id | credits | department
    -----------|-------------|----------|-------|-----------|---------|------------
    S100       | MATH101     | Fall     | A     | C1        | 4       | Mathematics
    S100       | CS201       | Fall     | B     | C2        | 3       | Computer Science
    S200       | MATH101     | Spring   | B+    | C3        | 4       | Mathematics



* *Left Anti-Join Output (Enrollments without catalog entries)**

::

    student_id | course_code | semester | grade | instructor
    -----------|-------------|----------|-------|-----------
    S300       | PHY301      | Fall     | A-    | Dr. Brown



* *Right Anti-Join Output (Catalog entries without enrollments)**

::

    course_id | course_code | semester | credits | department
    ----------|-------------|----------|---------|------------
    C4        | BIO202      | Fall     | 4       | Biology



::

    ---



:Example 5 — Retail Store Analysis with Sales Data
+++++++++++++++


* *Left DataFrame: Store Locations**

::

    store_id | store_name | state | square_footage
    ---------|------------|-------|---------------
    ST1      | Downtown   | CA    | 10000
    ST2      | Mall       | NY    | 15000
    ST3      | Plaza      | TX    | 8000
    ST4      | Corner     | FL    | 6000



* *Right DataFrame: Monthly Performance**

::

    store_code | month | total_sales | customer_count
    -----------|-------|-------------|---------------
    ST1        | Jan   | 150000      | 1200
    ST1        | Feb   | 165000      | 1350
    ST2        | Jan   | 200000      | 1500
    ST3        | Jan   | 90000       | 800
    ST5        | Jan   | 75000       | 600



* *Configuration**
* **Join By:** Specific Fields
* **Left Table Join Column:** store_id
* **Right Table Join Column:** store_code
* **Select Left Fields:** [store_id, store_name, state]
* **Select Right Fields:** [month, total_sales, customer_count]

* *Inner Join Output**

::

    store_id | store_name | state | month | total_sales | customer_count
    ---------|------------|-------|-------|-------------|---------------
    ST1      | Downtown   | CA    | Jan   | 150000      | 1200
    ST1      | Downtown   | CA    | Feb   | 165000      | 1350
    ST2      | Mall       | NY    | Jan   | 200000      | 1500
    ST3      | Plaza      | TX    | Jan   | 90000       | 800



* *Left Anti-Join Output (Stores without sales data)**

::

    store_id | store_name | state | square_footage
    ---------|------------|-------|---------------
    ST4      | Corner     | FL    | 6000



* *Right Anti-Join Output (Sales data without stores)**

::

    store_code | month | total_sales | customer_count
    -----------|-------|-------------|---------------
    ST5        | Jan   | 75000       | 600



::

    ---



:Example 6 — Position-Based Join for Time Series Alignment
+++++++++++++++


* *Left DataFrame: Forecast Data**

::

    period | forecast_revenue | growth_rate
    -------|------------------|------------
    Q1     | 500000           | 0.15
    Q2     | 550000           | 0.10
    Q3     | 600000           | 0.09
    Q4     | 650000           | 0.08



* *Right DataFrame: Actual Results**

::

    quarter | actual_revenue | variance
    --------|----------------|---------
    Q1      | 480000         | -20000
    Q2      | 560000         | 10000
    Q3      | 590000         | -10000



* *Configuration**
* **Join By:** Position
* **Select Left Fields:** [period, forecast_revenue]
* **Select Right Fields:** [actual_revenue, variance]
* **Rename Left Fields:** [quarter, forecast]
* **Rename Right Fields:** [actual, diff]

* *Inner Join Output**

::

    quarter | forecast | actual  | diff
    --------|----------|---------|--------
    Q1      | 500000   | 480000  | -20000
    Q2      | 550000   | 560000  | 10000
    Q3      | 600000   | 590000  | -10000



* *Left Anti-Join Output (Forecasts without actuals)**

::

    period | forecast_revenue | growth_rate
    -------|------------------|------------
    Q4     | 650000           | 0.08



::

    ---
