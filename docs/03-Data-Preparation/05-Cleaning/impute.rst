Impute Advanced
=========== 

It imputes missing or given value with constant value,mean, median or mode

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeImputeAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Columns
        - Columns to be processed for missing values
      * - strategy
        - Impute Strategy
        - Imputing Strategy
      * - replaceValue
        - Replace Value
        - Value to replace, when empty it replaces the missing values
      * - constants
        - Constant
        - Missing value will be replaced with constant.Applicable only when imputation strategy is constant


Details
-------


This node imputes missing values or replaces  specified values in the selected columns by mean, meadian, mode or constant.


Examples
-------


Incoming Dataframe has following rows and missing value / [NULL] for some rows:

+---+----+----+----+----+
| ID|  X1|  X2|  X3|  X4|
+---+----+----+----+----+
|  1|4.45| 5.6|null| 7.0|
|  2|5.83|5.72|2.55|10.0|
|  3|1.54|6.97|3.54| 3.0|
|  4|null|3.98|4.95| 2.0|
|  5| 3.1|null|8.42|null|
|  6|8.74| 6.1|1.91| 4.0|
|  7|null|0.01|8.07| 5.0|
|  8|7.51|6.31|5.94| 4.0|
|  9|1.21|4.74|1.91| 5.0|
| 10|1.85|7.02|null| 6.0|
+---+----+----+----+----+

If Impute Advanced node is configured to:
        selected column: X1 -> Imputation strategy ->Mean
        selected column: X2 -> Imputation strategy ->Median
        selected column: X3 -> Imputation strategy ->Mode
        selected column: X4 -> Imputation strategy ->Constant -> 123
        selcted column : X1 -> Imputation Strategy ->Median -> Replace value -> 3.1
        selected column: X2 -> Imputation Strategy ->Constant ->Replace value -> 0.01
Outgoing Dataframe would result as below:

+---+----+----+----+-------+
| ID|  X1|  X2|  X3|     X4|
+---+----+----+----+-------+
|  1|4.45| 5.6|1.91|    7.0|
|  2|5.83|5.72|2.55|   10.0|
|  3|1.54|6.97|3.54|    3.0|
|  4|4.28|3.98|4.95|    2.0|
|  5|4.28|5.72|8.42|  123.0|
|  6|8.74| 6.1|1.91|    4.0|
|  7|4.28| 1.0|8.07|    5.0|
|  8|7.51|6.31|5.94|    4.0|
|  9|1.21|4.74|1.91|    5.0|
| 10|1.85|7.02|1.91|    6.0|
+---+----+----+----+-------+

Similarly if one wants to replace a particular value by mean/median/mode/constant, This can be achieved by specifying replace value in the node configration.
