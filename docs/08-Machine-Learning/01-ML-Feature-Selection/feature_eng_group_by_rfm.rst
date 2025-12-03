Group By RFM Features
=========== 

This node computes feature engineering tasks such as group by, frequency, recency, average days between purchases, total value of purchases, and customer age. These are computed per user using the selected operations.

Input
--------------
It takes DataFrame(s) as input for processing.

Output
--------------
Returns engineered features as a DataFrame.

Type
--------- 

pyspark

Class
--------- 

fire.nodes.fe.NodeRFMFeatures

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - groupByCols
        - Group By Columns
        - Columns to group by
      * - frequency
        - Enable Frequency
        - Enable frequency count per user ID
      * - recency
        - Enable Recency
        - Enable recency computation (last purchase date) per user ID
      * - recencyDateCol
        - Recency Date Column
        - Date column to compute recency from
      * - avgDaysBetween
        - Enable Avg Days Between
        - Enable computation of average days between purchases
      * - avgDaysDateCol
        - Avg Days Date Column
        - Date column to compute average days between
      * - valueOfPurchase
        - Enable Value of Purchase
        - Enable total value of purchase per user
      * - sumCols
        - Columns to Sum
        - Numeric columns to sum per user
      * - customerAge
        - Enable Customer Age
        - Compute age of customer from DOB
      * - dobCol
        - Date of Birth Column
        - Column containing date of birth


Details
-------
Feature Engineering Node Details
---------------


The Feature Engineering node is designed to compute user-level features by applying various analytical operations such as frequency, recency, average days between events, total value of purchases, and customer age. These features are generated per group (e.g., per user ID) using the selected input columns and operations.



General:
+++++++++++++++



Group By Columns:
+++++++++++++++

Specifies the column(s) to group the input data by. Typically, this would be a user or customer identifier (e.g., user_id, customer_id). All other feature engineering computations are performed within each group.



Enable Frequency:
+++++++++++++++

When enabled, computes the frequency (i.e., count) of rows per group. Useful for understanding user activity levels.



Enable Recency:
+++++++++++++++

When enabled, calculates the number of days since the last recorded activity or event per group. Requires a date column to compute this from.



Recency Date Column:
+++++++++++++++

Specifies the column containing the date values for recency computation. Recency is calculated as the number of days between the maximum date per group and the current date.



Enable Avg Days Between:
+++++++++++++++

When enabled, computes the average number of days between consecutive activities or transactions per group.



Avg Days Date Column:
+++++++++++++++

Specifies the date column to use for computing the average time gap between consecutive records within each group.



Enable Value of Purchase:
+++++++++++++++

When enabled, computes the total value of purchases per group by summing selected numeric columns.



Columns to Sum:
+++++++++++++++

Specifies one or more numeric columns whose values are summed per group to calculate total value of purchases.



Enable Customer Age:
+++++++++++++++

When enabled, calculates the current age of the customer based on their date of birth.



Date of Birth Column:
+++++++++++++++

Specifies the column containing the customer's date of birth, which is used to compute their current age in years.



Output:
+++++++++++++++

The node outputs a DataFrame with the group-by columns and one or more additional columns, depending on the selected features:


* frequency: count
* recency: recency_days
* avgDaysBetween: avg_days_between
* valueOfPurchase: sum_<col_name> for each column selected in Columns to Sum
* customerAge: customer_age


Examples
-------
Feature Engineering Node Examples
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* userId: ["U1", "U1", "U2", "U2", "U2"]
* eventDate: ["2023-01-01", "2023-01-10", "2023-01-05", "2023-01-15", "2023-01-25"]
* amount: [100, 150, 200, 300, 500]
* dob: ["1990-04-01", "1990-04-01", "1985-08-20", "1985-08-20", "1985-08-20"]


The Feature Engineering node is configured as follows:


* Group By Columns: userId
* Enable Frequency: true
* Enable Recency: true
* Recency Date Column: eventDate
* Enable Avg Days Between: true
* Avg Days Date Column: eventDate
* Enable Value of Purchase: true
* Columns to Sum: amount
* Enable Customer Age: true
* Date of Birth Column: dob


Output:
+++++++++++++++


The node processes the DataFrame and produces the following result:


* userId: "U1"

frequency: 2

recency_days: (based on today - "2023-01-10")

avg_days_between: 9.0

sum_amount: 250

customer_age: 35



* userId: "U2"

frequency: 3

recency_days: (based on today - "2023-01-25")

avg_days_between: 10.0

sum_amount: 1000

customer_age: 39
