Time Series Features
=========== 

This node computes various time-series related features from a DataFrame containing transactional data.

Input
--------------
It takes a DataFrame with user, date, and optionally amount, item, and category columns.

Output
--------------
Returns the original DataFrame with new time-series feature columns appended.

Type
--------- 

pyspark

Class
--------- 

fire.nodes.fe.NodeTimeSeriesFeatures

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - userCol
        - User ID Column
        - Column representing the user or entity ID.
      * - dateCol
        - Date/Timestamp Column
        - Column representing the transaction date or timestamp.
      * - amountCol
        - Amount Column
        - Column representing the transaction amount (optional).
      * - itemCol
        - Item Column
        - Column representing the item purchased (optional).
      * - categoryCol
        - Category Column
        - Column representing the transaction category (optional).
      * - enable_days_since_last_transaction
        - Enable Days Since Last Transaction
        - Calculates the time elapsed since the user's last transaction.
      * - days_since_last_transaction_unit
        - Unit
        - Time unit for calculation.
      * - enable_days_until_next_transaction
        - Enable Days Until Next Transaction
        - Calculates the time remaining until the user's next transaction.
      * - days_until_next_transaction_unit
        - Unit
        - Time unit for calculation.
      * - enable_transaction_hour
        - Enable Transaction Hour
        - Extracts the hour from the transaction timestamp.
      * - enable_transaction_day_of_week
        - Enable Transaction Day of Week
        - Extracts the day of the week from the transaction timestamp.
      * - transaction_day_of_week_start
        - Week Start Day
        - Select the day to be considered as the start of the week (0).
      * - enable_transaction_day_of_month
        - Enable Transaction Day of Month
        - Extracts the day of the month from the transaction timestamp.
      * - enable_week_of_year
        - Enable Week of Year
        - Extracts the week of the year from the transaction timestamp.
      * - enable_is_weekend
        - Enable Is Weekend
        - Creates a binary flag indicating if the transaction occurred on a weekend.
      * - enable_is_month_start
        - Enable Is Month Start
        - Creates a binary flag if the transaction is at the start of the month.
      * - month_start_days
        - Start Days
        - Number of days from the start of the month to consider.
      * - enable_is_month_end
        - Enable Is Month End
        - Creates a binary flag if the transaction is at the end of the month.
      * - month_end_days
        - End Days
        - Day of the month from which to consider the end (e.g., 28 for last 3 days of Feb).
      * - enable_time_since_first_transaction
        - Enable Time Since First Transaction
        - Calculates the time elapsed since the user's very first transaction.
      * - time_since_first_transaction_unit
        - Unit
        - Time unit for calculation.
      * - enable_time_of_day_bin
        - Enable Time of Day Bin
        - Categorizes transactions into 'night', 'morning', 'afternoon', and 'evening'.
      * - enable_season
        - Enable Season
        - Assigns a season ('winter', 'spring', 'summer', 'autumn') to each transaction based on the month.
      * - enable_avg_time_between_txns
        - Enable Average Time Between Transactions
        - Calculates the average time between a user's transactions.
      * - avg_time_between_txns_unit
        - Unit
        - Time unit for calculation.
      * - enable_rolling_transaction_count
        - Enable Rolling Transaction Count
        - Counts the number of transactions in a rolling window.
      * - rolling_transaction_count_window
        - Window Size (days)
        - Window size for the rolling count.
      * - enable_rolling_amount_mean
        - Enable Rolling Amount Mean (Required field : Amount)
        - Computes a rolling average of transaction amounts over a defined window
      * - rolling_amount_mean_window
        - Window Size (days)
        - Window size for the rolling mean.
      * - enable_days_since_last_same_item
        - Enable Days Since Last Same Item (Required field : Item)
        - Calculates time since the last purchase of the same item
      * - days_since_last_same_item_unit
        - Unit
        - Time unit for calculation.
      * - enable_days_since_last_same_category
        - Enable Days Since Last Same Category (Required field : Category)
        - Calculates time since the last purchase in the same category.
      * - days_since_last_same_category_unit
        - Unit
        - Time unit for calculation.


Details
-------
Time Series Features Node Details
---------------


The Time Series Features node is designed to compute a variety of time-series related features from transactional data stored in a DataFrame. It processes user-level data to generate features such as time since last transaction, transaction hour, day of the week, and more, based on the configured options. These features are appended as new columns to the input DataFrame.



General:
+++++++++++++++



User ID Column:
+++++++++++++++

Specifies the column containing the user or entity identifier (e.g., user_id, customer_id). This is a required field used for partitioning the data for user-level feature calculations.



Date/Timestamp Column:
+++++++++++++++

Specifies the column containing the date or timestamp of the transactions. This is a required field used for all time-based feature computations.



Amount Column:
+++++++++++++++

Specifies an optional column containing the transaction amount (e.g., purchase value). Required for features like rolling amount mean.



Item Column:
+++++++++++++++

Specifies an optional column containing the item purchased in the transaction. Required for computing days since last same item.



Category Column:
+++++++++++++++

Specifies an optional column containing the transaction category. Required for computing days since last same category.



Enable Days Since Last Transaction:
+++++++++++++++

When enabled, calculates the time elapsed since the user's last transaction in the specified time unit (days or hours).



Days Since Last Transaction Unit:
+++++++++++++++

Selects the time unit (days or hours) for the days since last transaction calculation.



Enable Days Until Next Transaction:
+++++++++++++++

When enabled, calculates the time remaining until the user's next transaction in the specified time unit (days or hours).



Days Until Next Transaction Unit:
+++++++++++++++

Selects the time unit (days or hours) for the days until next transaction calculation.



Enable Transaction Hour:
+++++++++++++++

When enabled, extracts the hour of the day (0-23) from the transaction timestamp.



Enable Transaction Day of Week:
+++++++++++++++

When enabled, extracts the day of the week from the transaction timestamp, with the week start day configurable (e.g., Monday as 0).



Week Start Day:
+++++++++++++++

Selects the day considered as the start of the week (0) for day of week calculations (e.g., Monday, Tuesday, etc.).



Enable Transaction Day of Month:
+++++++++++++++

When enabled, extracts the day of the month (1-31) from the transaction timestamp.



Enable Week of Year:
+++++++++++++++

When enabled, extracts the week of the year (1-52) from the transaction timestamp, with Monday as the week start.



Enable Is Weekend:
+++++++++++++++

When enabled, creates a binary flag (1 or 0) indicating whether the transaction occurred on a weekend (typically Saturday and Sunday).



Enable Is Month Start:
+++++++++++++++

When enabled, creates a binary flag (1 or 0) indicating whether the transaction occurred at the start of the month, based on a configurable number of days.



Start Days:
+++++++++++++++

Specifies the number of days from the start of the month to consider as the "month start" (e.g., 2 for the first two days).



Enable Is Month End:
+++++++++++++++

When enabled, creates a binary flag (1 or 0) indicating whether the transaction occurred at the end of the month, based on a configurable day threshold.



End Days:
+++++++++++++++

Specifies the day of the month from which to consider the "month end" (e.g., 28 for the last few days of the month).



Enable Time Since First Transaction:
+++++++++++++++

When enabled, calculates the time elapsed since the user's first recorded transaction in the specified time unit (days or hours).



Time Since First Transaction Unit:
+++++++++++++++

Selects the time unit (days or hours) for the time since first transaction calculation.



Enable Time of Day Bin:
+++++++++++++++

When enabled, categorizes transactions into time-of-day bins: 'night' (0-5), 'morning' (6-11), 'afternoon' (12-17), or 'evening' (18-23).



Enable Season:
+++++++++++++++

When enabled, assigns a season ('winter', 'spring', 'summer', or 'autumn') to each transaction based on the month (e.g., December-February is winter).



Enable Average Time Between Transactions:
+++++++++++++++

When enabled, calculates the average time between a user's consecutive transactions in the specified time unit (days or hours).



Average Time Between Transactions Unit:
+++++++++++++++

Selects the time unit (days or hours) for the average time between transactions calculation.



Enable Rolling Transaction Count:
+++++++++++++++

When enabled, counts the number of transactions within a rolling time window (in days).



Rolling Transaction Count Window:
+++++++++++++++

Specifies the window size (in days) for the rolling transaction count.



Enable Rolling Amount Mean:
+++++++++++++++

When enabled, computes the rolling average of transaction amounts over a specified window (in days). Requires the Amount Column.



Rolling Amount Mean Window:
+++++++++++++++

Specifies the window size (in days) for the rolling amount mean.



Enable Days Since Last Same Item:
+++++++++++++++

When enabled, calculates the time since the last purchase of the same item. Requires the Item Column.



Days Since Last Same Item Unit:
+++++++++++++++

Selects the time unit (days or hours) for the days since last same item calculation.



Enable Days Since Last Same Category:
+++++++++++++++

When enabled, calculates the time since the last purchase in the same category. Requires the Category Column.



Days Since Last Same Category Unit:
+++++++++++++++

Selects the time unit (days or hours) for the days since last same category calculation.



Output:
+++++++++++++++

The node outputs the original DataFrame with additional columns based on the enabled features:


* days_since_last_transaction or hours_since_last_transaction
* days_until_next_transaction or hours_until_next_transaction
* transaction_hour
* transaction_day_of_week
* transaction_day_of_month
* week_of_year
* is_weekend
* is_month_start
* is_month_end
* time_since_first_transaction_days or time_since_first_transaction_hours
* time_of_day_bin
* season
* avg_time_between_txns_days or avg_time_between_txns_hours
* rolling_transaction_count_<window>d
* rolling_amount_mean_<window>d
* days_since_last_same_item or hours_since_last_same_item
* days_since_last_same_category or hours_since_last_same_category


Examples
-------
Time Series Features Node Examples
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* userId: ["U1", "U1", "U2", "U2", "U2"]
* eventDate: ["2023-01-01 08:00:00", "2023-01-10 14:00:00", "2023-01-05 22:00:00", "2023-01-15 12:00:00", "2023-01-25 18:00:00"]
* amount: [100.0, 150.0, 200.0, 300.0, 500.0]
* item: ["itemA", "itemB", "itemA", "itemA", "itemB"]
* category: ["cat1", "cat2", "cat1", "cat1", "cat2"]


The Time Series Features node is configured as follows:


* User ID Column: userId
* Date/Timestamp Column: eventDate
* Amount Column: amount
* Item Column: item
* Category Column: category
* Enable Days Since Last Transaction: true
* Days Since Last Transaction Unit: days
* Enable Transaction Hour: true
* Enable Transaction Day of Week: true
* Week Start Day: Monday
* Enable Is Weekend: true
* Enable Time of Day Bin: true
* Enable Season: true
* Enable Rolling Transaction Count: true
* Rolling Transaction Count Window: 30
* Enable Rolling Amount Mean: true
* Rolling Amount Mean Window: 7
* Enable Days Since Last Same Item: true
* Days Since Last Same Item Unit: days
* Enable Days Since Last Same Category: true
* Days Since Last Same Category Unit: days


Output:
+++++++++++++++


The node processes the DataFrame and produces the following result (values are illustrative, assuming today is 2023-02-01):


* userId: "U1", eventDate: "2023-01-01 08:00:00", amount: 100.0, item: "itemA", category: "cat1"

days_since_last_transaction: null

transaction_hour: 8

transaction_day_of_week: 0

is_weekend: 0

time_of_day_bin: "morning"

season: "winter"

rolling_transaction_count_30d: 1

rolling_amount_mean_7d: 100.0

days_since_last_same_item: null

days_since_last_same_category: null


* userId: "U1", eventDate: "2023-01-10 14:00:00", amount: 150.0, item: "itemB", category: "cat2"

days_since_last_transaction: 9

transaction_hour: 14

transaction_day_of_week: 2

is_weekend: 0

time_of_day_bin: "afternoon"

season: "winter"

rolling_transaction_count_30d: 2

rolling_amount_mean_7d: 125.0

days_since_last_same_item: null

days_since_last_same_category: null


* userId: "U2", eventDate: "2023-01-05 22:00:00", amount: 200.0, item: "itemA", category: "cat1"

days_since_last_transaction: null

transaction_hour: 22

transaction_day_of_week: 4

is_weekend: 0

time_of_day_bin: "evening"

season: "winter"

rolling_transaction_count_30d: 1

rolling_amount_mean_7d: 200.0

days_since_last_same_item: null

days_since_last_same_category: null


* userId: "U2", eventDate: "2023-01-15 12:00:00", amount: 300.0, item: "itemA", category: "cat1"

days_since_last_transaction: 10

transaction_hour: 12

transaction_day_of_week: 0

is_weekend: 0

time_of_day_bin: "afternoon"

season: "winter"

rolling_transaction_count_30d: 2

rolling_amount_mean_7d: 250.0

days_since_last_same_item: 10

days_since_last_same_category: 10


* userId: "U2", eventDate: "2023-01-25 18:00:00", amount: 500.0, item: "itemB", category: "cat2"

days_since_last_transaction: 10

transaction_hour: 18

transaction_day_of_week: 3

is_weekend: 0

time_of_day_bin: "evening"

season: "winter"

rolling_transaction_count_30d: 3

rolling_amount_mean_7d: 400.0

days_since_last_same_item: null

days_since_last_same_category: null
