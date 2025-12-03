Window Function
=========== 

This node applies window functions to the input DataFrame, allowing operations like ranking, analytical, and aggregate functions over specified windows.

Input
--------------
It takes one DataFrame as input from the previous node.

Output
--------------
This node outputs a DataFrame with additional columns computed from the window functions.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeWindowFunction

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - PartitionBy
        - PartitionBy
        - 
      * - partitionCols
        - Partition Column Names
        - List of columns to partition by
      * - order
        - OrderBy
        - 
      * - orderCols
        - Order Columns
        - List of columns to order by
      * - orderDirections
        - Order Directions
        - Directions (ASC or DESC) corresponding to each order column
      * - frame
        - Frame
        - 
      * - useFrame
        - Specify Frame
        - Unselecting this uses default frame specifications
      * - frameType
        - Frame Type
        - Type of frame: ROW for row-based, RANGE for value-based
      * - frameStart
        - Frame Start
        - Frame start boundary, e.g., UNBOUNDED_PRECEDING, CURRENT_ROW, or a number like -5
      * - frameEnd
        - Frame End
        - Frame end boundary, e.g., CURRENT_ROW, UNBOUNDED_FOLLOWING, or a number like 0
      * - windowUses
        - Window Use
        - 
      * - windowTargetColumns
        - Column Name
        - Output Column Name
      * - windowExpressionsArr
        - Expression
        - Expression to create new columns


Details
-------
Window Function Node Details
---------------


This node enables the application of window functions on a DataFrame, supporting partitioning, ordering, framing, and various window expressions like ranking, analytical, and aggregate functions.

It uses Spark's Window API to perform calculations over defined windows without reducing the number of rows.


The configuration includes:


* **Window Configuration Tab**: Partitioning to group data, ordering to sort within partitions, and framing to define the window boundaries (row or range based).
* **Window Functions Tab**: Specification of the functions and target columns to apply.


All window functions share the same partition, order, and frame configuration.

For different configurations, chain multiple nodes.


Examples
-------
Window Function Node Examples
---------------


::

    ---



:Example 1 — Ranking and Running Totals
+++++++++++++++



* *Incoming DataFrame**

::

    customer_id | order_date | amount
    ------------|-------------|--------
    1 | 2020-01-01 | 100
    1 | 2020-02-01 | 200
    1 | 2020-03-01 | 150
    2 | 2020-01-15 | 300
    2 | 2020-02-15 | 400


* *Configuration**
* **Partition Columns:** customer_id
* **Order Columns:** order_date
* **Order Directions:** ASC
* **Frame Type:** ROW
* **Frame Start:** UNBOUNDED_PRECEDING
* **Frame End:** CURRENT_ROW
* **Window Uses:**
* order_number = row_number()
* running_total = sum(amount)
* running_avg = avg(amount)

* *Final Output**

::

    customer_id | order_date | amount | order_number | running_total | running_avg
    ------------|-------------|--------|--------------|---------------|------------
    1 | 2020-01-01 | 100 | 1 | 100 | 100.0
    1 | 2020-02-01 | 200 | 2 | 300 | 150.0
    1 | 2020-03-01 | 150 | 3 | 450 | 150.0
    2 | 2020-01-15 | 300 | 1 | 300 | 300.0
    2 | 2020-02-15 | 400 | 2 | 700 | 350.0


::

    ---



:Example 2 — Previous and Next Values
+++++++++++++++


* *Configuration**
* **Partition Columns:** customer_id
* **Order Columns:** order_date
* **Order Directions:** ASC
* **Use Frame:** false
* **Window Uses:**
* prev_amount = lag(amount, 1)
* next_amount = lead(amount, 1)

* *Output**

::

    customer_id | order_date | amount | prev_amount | next_amount
    ------------|-------------|--------|--------------|-------------
    1 | 2020-01-01 | 100 | null | 200
    1 | 2020-02-01 | 200 | 100 | 150
    1 | 2020-03-01 | 150 | 200 | null
    2 | 2020-01-15 | 300 | null | 400
    2 | 2020-02-15 | 400 | 300 | null


::

    ---



:Example 3 — Range Frame Based on Amount
+++++++++++++++


* *Incoming DataFrame**

::

    customer_id | txn_amount | txn_date
    ------------|-------------|----------
    1 | 100 | 2020-01-01
    1 | 200 | 2020-01-02
    1 | 250 | 2020-01-05
    1 | 300 | 2020-01-10


* *Configuration**
* **Partition Columns:** customer_id
* **Order Columns:** txn_amount
* **Order Directions:** ASC
* **Use Frame:** true
* **Frame Type:** RANGE
* **Frame Start:** -100
* **Frame End:** 0
* **Window Uses:**
* range_sum = sum(txn_amount)

* *Output**

::

    customer_id | txn_amount | range_sum
    ------------|-------------|-----------
    1 | 100 | 100
    1 | 200 | 300
    1 | 250 | 450
    1 | 300 | 550


::

    ---



:Example 4 — Custom Row Frame (Last 2 Rows + Current)
+++++++++++++++


* *Incoming DataFrame**

::

    id | value
    ---|-------
    1 | 10
    2 | 20
    3 | 30
    4 | 40
    5 | 50


* *Configuration**
* **Order Columns:** id
* **Order Directions:** ASC
* **Use Frame:** true
* **Frame Type:** ROW
* **Frame Start:** -2
* **Frame End:** 0
* **Window Uses:**
* moving_avg = avg(value)

* *Output**

::

    id | value | moving_avg
    ---|--------|------------
    1 | 10 | 10.0
    2 | 20 | 15.0
    3 | 30 | 20.0
    4 | 40 | 30.0
    5 | 50 | 40.0


::

    ---



:Example 5 — Department Totals and Averages
+++++++++++++++


* *Incoming DataFrame**

::

    emp_id | name | dept | salary
    -------|------|------|--------
    1 | John | IT | 50000
    2 | Alice | IT | 70000
    3 | Bob | HR | 60000
    4 | Eva | HR | 65000
    5 | Tom | Finance | 80000


* *Configuration**
* **Partition Columns:** dept
* **Use Frame:** false
* **Window Uses:**
* dept_total = sum(salary)
* dept_avg = avg(salary)

* *Output**

::

    emp_id | name | dept | salary | dept_total | dept_avg
    -------|------|------|--------|-------------|---------
    1 | John | IT | 50000 | 120000 | 60000.0
    2 | Alice | IT | 70000 | 120000 | 60000.0
    3 | Bob | HR | 60000 | 125000 | 62500.0
    4 | Eva | HR | 65000 | 125000 | 62500.0
    5 | Tom | Finance | 80000 | 80000 | 80000.0


::

    ---



:Example 6 — Class Grouping Based on Description Continuity
+++++++++++++++


* *Incoming DataFrame**

::

    RecordID | Description
    ----------|-------------
    1 | A
    2 | null
    3 | B
    4 | C
    5 | null
    6 | D
    7 | null
    8 | null
    9 | E
    10 | F


* *Configuration**
* **Order Columns:** RecordID
* **Order Directions:** ASC
* **Use Frame:** false
* **Window Uses:**
* prevDesc = lag(Description, 1)
* start = CASE WHEN prevDesc IS NULL OR prevDesc='' OR Description IS NULL OR Description='' THEN 1 ELSE 0 END
* startDesc = CASE WHEN start = 1 THEN Description ELSE NULL END
* Class = last(startDesc, true)

* *Final Output**

::

    RecordID | Description | prevDesc | start | startDesc | Class
    ----------|-------------|-----------|--------|------------|--------
    1 | A | null | 1 | A | A
    2 | null | A | 1 | null | A
    3 | B | null | 1 | B | B
    4 | C | B | 0 | null | B
    5 | null | C | 1 | null | B
    6 | D | null | 1 | D | D
    7 | null | D | 1 | null | D
    8 | null | null | 1 | null | D
    9 | E | null | 1 | E | E
    10 | F | E | 0 | null | E


* *Explanation:**

This configuration identifies when a new group starts based on missing or null values in `Description`.

The `Class` column propagates the most recent non-null `startDesc` value downward, effectively assigning each row to its nearest preceding description group.


::

    ---



:Example 7 — Ranking and Percent Rank
+++++++++++++++



* *Incoming DataFrame**

::

    dept | emp | salary
    ------|------|--------
    IT | John | 70000
    IT | Alice | 90000
    IT | Mike | 85000
    HR | Bob | 60000
    HR | Eva | 75000


* *Configuration**
* **Partition Columns:** dept
* **Order Columns:** salary
* **Order Directions:** DESC
* **Use Frame:** false
* **Window Uses:**
* rank_in_dept = rank()
* pct_in_dept = percent_rank()

* *Output**

::

    dept | emp | salary | rank_in_dept | pct_in_dept
    ------|------|--------|---------------|-------------
    IT | Alice | 90000 | 1 | 0.0
    IT | Mike | 85000 | 2 | 0.5
    IT | John | 70000 | 3 | 1.0
    HR | Eva | 75000 | 1 | 0.0
    HR | Bob | 60000 | 2 | 1.0


::

    ---



:Example 8 — Cumulative Distribution and Dense Rank
+++++++++++++++


* *Incoming DataFrame**

::

    category | sales
    ----------|-------
    A | 100
    A | 150
    A | 200
    B | 50
    B | 100
    B | 200


* *Configuration**
* **Partition Columns:** category
* **Order Columns:** sales
* **Order Directions:** ASC
* **Use Frame:** false
* **Window Uses:**
* dense_rank = dense_rank()
* cume_dist_val = cume_dist()

* *Output**

::

    category | sales | dense_rank | cume_dist_val
    ----------|-------|-------------|--------------
    A | 100 | 1 | 0.3333
    A | 150 | 2 | 0.6666
    A | 200 | 3 | 1.0000
    B | 50 | 1 | 0.3333
    B | 100 | 2 | 0.6666
    B | 200 | 3 | 1.0000


::

    ---
