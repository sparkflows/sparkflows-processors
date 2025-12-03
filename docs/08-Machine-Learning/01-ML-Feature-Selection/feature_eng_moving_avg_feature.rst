Moving Average Features
=========== 

This node computes various global moving average features from a DataFrame containing transactional data.

Input
--------------
It takes a DataFrame with date, and optionally user, amount, quantity columns.

Output
--------------
Returns the original DataFrame with new global moving average feature columns appended.

Type
--------- 

pyspark

Class
--------- 

fire.nodes.fe.NodeMovingAverageFeatures

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - dateCol
        - Date/Timestamp Column
        - Column representing the transaction date or timestamp.
      * - userCol
        - User ID Column
        - Column representing the user or entity ID.
      * - amountCol
        - Amount Column
        - Column representing the transaction amount.
      * - quantityCol
        - Quantity Column
        - Column representing the quantity.
      * - enable_global_moving_avg_txn_count_per_day
        - Enable Global Moving Avg Txn Count Per Day
        - Global average transaction count per day over the window.
      * - global_moving_avg_txn_count_per_day_window
        - Window Size (days)
        - 
      * - enable_global_moving_avg_gap_days
        - Enable Global Moving Avg Gap Days
        - Global average gap days between transactions over the window.
      * - global_moving_avg_gap_days_window
        - Window Size (days)
        - 
      * - enable_global_hourly_avg_txn_count
        - Enable Global Hourly Avg Txn Count
        - Global average transaction count per hour over the window.
      * - global_hourly_avg_txn_count_window_hours
        - Window Size (hours)
        - 
      * - enable_global_daily_avg_amount
        - Enable Global Daily Avg Amount (Required: Amount)
        - Global average amount per day over the window.
      * - global_daily_avg_amount_window
        - Window Size (days)
        - 
      * - enable_global_moving_avg_amount
        - Enable Global Moving Avg Amount (Required: Amount)
        - Global average transaction amount over the window.
      * - global_moving_avg_amount_window
        - Window Size (days)
        - 
      * - enable_global_moving_avg_sales_per_day
        - Enable Global Moving Avg Sales Per Day (Required: Quantity)
        - Global average sales (quantity) per day over the window.
      * - global_moving_avg_sales_per_day_window
        - Window Size (days)
        - 
      * - enable_global_moving_avg_unique_users_per_day
        - Enable Global Moving Avg Unique Users Per Day (Required: User)
        - Global average unique users per day over the window.
      * - global_moving_avg_unique_users_per_day_window
        - Window Size (days)
        - 


Details
-------
Moving Average Features Node Details
---------------


The Moving Average Features node is designed to compute global moving average features from transactional data stored in a DataFrame. It calculates metrics such as average transaction counts, gap days, amounts, sales quantities, and unique users over specified time windows. These features are appended as new columns to the input DataFrame, providing insights into global trends across all transactions.



General:
+++++++++++++++



Date/Timestamp Column:
+++++++++++++++

Specifies the column containing the date or timestamp of the transactions. This is a required field used for all time-based feature computations.



User ID Column:
+++++++++++++++

Specifies an optional column containing the user or entity identifier (e.g., user_id, customer_id). Required for computing global moving average unique users per day.



Amount Column:
+++++++++++++++

Specifies an optional column containing the transaction amount (e.g., purchase value). Required for features like global moving average amount and global daily average amount.



Quantity Column:
+++++++++++++++

Specifies an optional column containing the quantity of items in the transaction. Required for computing global moving average sales per day.



Enable Global Moving Avg Txn Count Per Day:
+++++++++++++++

When enabled, calculates the global average transaction count per day over a specified window (in days).



Global Moving Avg Txn Count Per Day Window:
+++++++++++++++

Specifies the window size (in days) for the global moving average transaction count per day.



Enable Global Moving Avg Gap Days:
+++++++++++++++

When enabled, calculates the global average gap days between transactions over a specified window.



Global Moving Avg Gap Days Window:
+++++++++++++++

Specifies the window size (in days) for the global moving average gap days calculation.



Enable Global Hourly Avg Txn Count:
+++++++++++++++

When enabled, calculates the global average transaction count per hour over a specified window (in hours).



Global Hourly Avg Txn Count Window:
+++++++++++++++

Specifies the window size (in hours) for the global hourly average transaction count.



Enable Global Daily Avg Amount:
+++++++++++++++

When enabled, calculates the global average transaction amount per day over a specified window. Requires the Amount Column.



Global Daily Avg Amount Window:
+++++++++++++++

Specifies the window size (in days) for the global daily average amount calculation.



Enable Global Moving Avg Amount:
+++++++++++++++

When enabled, calculates the global average transaction amount over a specified window. Requires the Amount Column.



Global Moving Avg Amount Window:
+++++++++++++++

Specifies the window size (in days) for the global moving average amount calculation.



Enable Global Moving Avg Sales Per Day:
+++++++++++++++

When enabled, calculates the global average sales (quantity) per day over a specified window. Requires the Quantity Column.



Global Moving Avg Sales Per Day Window:
+++++++++++++++

Specifies the window size (in days) for the global moving average sales per day calculation.



Enable Global Moving Avg Unique Users Per Day:
+++++++++++++++

When enabled, calculates the global average number of unique users per day over a specified window. Requires the User ID Column.



Global Moving Avg Unique Users Per Day Window:
+++++++++++++++

Specifies the window size (in days) for the global moving average unique users per day calculation.



Output:
+++++++++++++++

The node outputs the original DataFrame with additional columns based on the enabled features:


* moving_avg_amount_<window>d
* moving_avg_txn_count_per_day_<window>d
* moving_avg_gap_days_<window>d
* moving_avg_sales_per_day_<window>d
* moving_avg_unique_users_per_day_<window>d
* daily_avg_amount_<window>d
* hourly_avg_txn_count_per_hour_<window>h


Examples
-------
Moving Average Features Node Examples
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* eventDate: ["2023-01-01 08:00:00", "2023-01-01 12:00:00", "2023-01-02 10:00:00", "2023-01-03 14:00:00", "2023-01-04 18:00:00"]
* userId: ["U1", "U2", "U1", "U2", "U3"]
* amount: [100.0, 150.0, 200.0, 300.0, 500.0]
* quantity: [2, 3, 1, 4, 5]


The Moving Average Features node is configured as follows:


* Date/Timestamp Column: eventDate
* User ID Column: userId
* Amount Column: amount
* Quantity Column: quantity
* Enable Global Moving Avg Txn Count Per Day: true
* Global Moving Avg Txn Count Per Day Window: 7
* Enable Global Moving Avg Gap Days: true
* Global Moving Avg Gap Days Window: 7
* Enable Global Hourly Avg Txn Count: true
* Global Hourly Avg Txn Count Window: 24
* Enable Global Daily Avg Amount: true
* Global Daily Avg Amount Window: 7
* Enable Global Moving Avg Amount: true
* Global Moving Avg Amount Window: 7
* Enable Global Moving Avg Sales Per Day: true
* Global Moving Avg Sales Per Day Window: 7
* Enable Global Moving Avg Unique Users Per Day: true
* Global Moving Avg Unique Users Per Day Window: 7


Output:
+++++++++++++++


The node processes the DataFrame and produces the following result (values are illustrative, assuming calculations are based on the input data):


* eventDate: "2023-01-01 08:00:00", userId: "U1", amount: 100.0, quantity: 2

moving_avg_txn_count_per_day_7d: 0.2857 (2 transactions over 7 days)

moving_avg_gap_days_7d: null (insufficient data for gap calculation)

hourly_avg_txn_count_per_hour_24h: 0.0833 (2 transactions over 24 hours)

daily_avg_amount_7d: 125.0 (250.0 total amount over 2 days)

moving_avg_amount_7d: 35.7143 (250.0 total amount over 7 days)

moving_avg_sales_per_day_7d: 0.7143 (5 total quantity over 7 days)

moving_avg_unique_users_per_day_7d: 1.0 (2 unique users over 2 days)


* eventDate: "2023-01-01 12:00:00", userId: "U2", amount: 150.0, quantity: 3

moving_avg_txn_count_per_day_7d: 0.2857

moving_avg_gap_days_7d: 0.1667 (4 hours gap converted to days)

hourly_avg_txn_count_per_hour_24h: 0.0833

daily_avg_amount_7d: 125.0

moving_avg_amount_7d: 35.7143

moving_avg_sales_per_day_7d: 0.7143

moving_avg_unique_users_per_day_7d: 1.0


* eventDate: "2023-01-02 10:00:00", userId: "U1", amount: 200.0, quantity: 1

moving_avg_txn_count_per_day_7d: 0.4286 (3 transactions over 7 days)

moving_avg_gap_days_7d: 0.5 (1 day gap)

hourly_avg_txn_count_per_hour_24h: 0.0417 (1 transaction over 24 hours)

daily_avg_amount_7d: 175.0 (350.0 total amount over 2 days)

moving_avg_amount_7d: 50.0 (350.0 total amount over 7 days)

moving_avg_sales_per_day_7d: 0.8571 (6 total quantity over 7 days)

moving_avg_unique_users_per_day_7d: 1.0


* eventDate: "2023-01-03 14:00:00", userId: "U2", amount: 300.0, quantity: 4

moving_avg_txn_count_per_day_7d: 0.5714 (4 transactions over 7 days)

moving_avg_gap_days_7d: 0.6667 (average of 1 day and 1 day gaps)

hourly_avg_txn_count_per_hour_24h: 0.0417

daily_avg_amount_7d: 216.6667 (650.0 total amount over 3 days)

moving_avg_amount_7d: 92.8571 (650.0 total amount over 7 days)

moving_avg_sales_per_day_7d: 1.4286 (10 total quantity over 7 days)

moving_avg_unique_users_per_day_7d: 1.0


* eventDate: "2023-01-04 18:00:00", userId: "U3", amount: 500.0, quantity: 5

moving_avg_txn_count_per_day_7d: 0.7143 (5 transactions over 7 days)

moving_avg_gap_days_7d: 0.75 (average of 1, 1, and 1 day gaps)

hourly_avg_txn_count_per_hour_24h: 0.0417

daily_avg_amount_7d: 287.5 (1150.0 total amount over 4 days)

moving_avg_amount_7d: 164.2857 (1150.0 total amount over 7 days)

moving_avg_sales_per_day_7d: 2.1429 (15 total quantity over 7 days)

moving_avg_unique_users_per_day_7d: 1.0
