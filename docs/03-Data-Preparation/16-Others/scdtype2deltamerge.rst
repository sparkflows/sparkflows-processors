SCDType2DeltaMerge
===========

It is a Delta merge operation that stores and manages both current and historical data over time.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeSCDType2DeltaMerge

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - targetType
        - Target Type
        - Target Type Table or Path
      * - targetLocation
        - Target Delta Path
        - Delta Path of the target location
      * - tableName
        - TableName
        - TableName
      * - keyColumns
        - Key Columns
        - Merge Check.
      * - active_flag_col
        - Active Flag Column
        - Used to mark which record is the current active one.
      * - active_flag_vals
        - Active Flag Value
        - True or False OR 1 or 0.
      * - start_date_col
        - Start Date Column Name
        - Column Name when a particular version of a record became valid or active
      * - end_date_col
        - End Date Column Name
        - Column Name when a particular version of a record became invalid or inactive
      * - start_date_val
        - Start Date Column Value
        - date value for particular version of a record became valid or active
      * - end_date_val
        - End Date Column Value
        - date value for a particular version of a record became valid or active


Details
-------
SCDType2 Delta Merge Node Details
+++++++++++++++


It is a Delta merge operation that stores and manages both current and historical data over time.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL: Choose how the data should be stored (e.g., DEFAULT, DISK_ONLY).
* TARGET TYPE: Select the type of target for the merge operation. This could be a Delta Lake table or a path to a directory.
* TARGET DELTA PATH: If "TARGET TYPE" is set to "Delta", specify the directory where the Delta Lake table is located. Use the "Browse" button to navigate and select the location.
* TABLENAME: If "TARGET TYPE" is set to "Table", specify the name of the Delta Lake table.
* KEY COLUMNS: Specify the column(s) that uniquely identify rows in the dimension table (e.g., customer_id, product_id). These columns are used to match rows between the source DataFrame and the target Delta Lake table. Select the key column(s) from the "Available" list and move them to the "Selected" list using the arrow buttons.
* ACTIVE FLAG COLUMN: Specify the name of the column in the Delta Lake table that indicates whether a record is currently active. This column is typically a boolean or flag column (e.g., is_current, is_active).
* ACTIVE FLAG VALUE: Specify the value that represents an "active" record in the ACTIVE FLAG COLUMN. This is usually true or 1, but it could be a different value depending on your data.
* START DATE COLUMN NAME: Specify the name of the column in the Delta Lake table that will store the start date of a record's validity. This column is used in SCD2 to track when a particular version of a record became active (e.g., effective_start_date, valid_from).
* END DATE COLUMN NAME: Specify the name of the column in the Delta Lake table that will store the end date of a record's validity. This column is used in SCD2 to track when a particular version of a record became inactive (e.g., effective_end_date, valid_to).
* START DATE COLUMN VALUE: Specify the value to be used for the START DATE COLUMN when a new record is inserted or an existing record is updated. This is often a function like current_date() to use the current date, but it could be a literal value or an expression.
* END DATE COLUMN VALUE: Specify the value to be used for the END DATE COLUMN when a new record is inserted or an existing record is updated. This is often a very large date in the future (to represent "infinity") or a function like current_date() to use the current date (if you're updating the end date of the previous record).


Examples
-------
SCD Type 2 Delta Merge Node Examples
+++++++++++++++



Example of Performing an SCD2 Merge
+++++++++++++++


* OUTPUT STORAGE LEVEL: DEFAULT
* TARGET TYPE: Delta
* TARGET DELTA PATH: /user/hive/warehouse/dim_customers
* KEY COLUMNS: customer_id
* ACTIVE FLAG COLUMN: is_current
* ACTIVE FLAG VALUE: true
* START DATE COLUMN NAME: effective_start_date
* END DATE COLUMN NAME: effective_end_date
* START DATE COLUMN VALUE: current_date()
* END DATE COLUMN VALUE: date_add(current_date(), 10000) (adding 10000 days to represent a date far in the future)


This configuration would:

Perform an SCD2 merge on the dim_customers Delta Lake table.

Use customer_id to match rows.

Use is_current as the active flag column, with true representing active records.

Use effective_start_date and effective_end_date to track the validity period of each record.

Set the effective_start_date to the current date for new and updated records.

Set the effective_end_date to a date far in the future for new and updated records.

This setup ensures that you maintain a full history of changes in your customer dimension table, allowing you to analyze customer data over time.
