DeltaMerge
=========== 

Insert, delete and update data using the Delta merge command.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDeltaMerge

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - targetLocation
        - TargetPath
        - Path of the target location
      * - sourceAlias
        - Source Alias
        - Alias to use for the source DataFrame
      * - targetAlias
        - Target Alias
        - Alias to use for existing target Delta table
      * - mergeCondition
        - Merge Condition
        - Condition to merge data from source DataFrame to target table, which would be used to perform update, delete, or insert actions as specified.
      * - whenMatchedUpdate
        - When Matched Update
        - 
      * - whenMatchedUpdateAction
        - WhenMatched Update Action
        - Update the row from Source that already exists in Target based on Merge Condition.
      * - whenMatchedUpdateCondition
        - Merge Condition
        - Optional additional condition for updating row. If specified then it must evaluate to true for the row to be updated.
      * - whenMatchedUpdateTargetColumns
        - Target Columns
        - Target Column
      * - whenMatchedUpdateExpressions
        - Expressions
        - Replace default update with expression
      * - whenMatchedDelete
        - When Matched Delete
        - 
      * - whenMatchedDeleteAction
        - WhenMatched Delete Action
        - Delete rows if Merge Condition and the optional additional condition evaluates to true.
      * - whenMatchedDeleteCondition
        - WhenMatched Delete Condition
        - Optional additional condition for deleting row. If a condition is specified then it must evaluate to true for the row to be deleted.
      * - whenNotMatched
        - When Not Matched
        - 
      * - whenNotMatchedAction
        - WhenNot Matched Action
        - The action to perform if the row from Source is not present in Target based on Merge Condition
      * - whenNotMatchedCondition
        - WhenNot Matched Condition
        - Optional condition for inserting row. If a condition is specified then it must evaluate to true for the row to be updated.
      * - whenNotMatchedTargetColumns
        - Target Columns
        - Target Column
      * - whenNotMatchedExpressions
        - Expressions
        - Replace default insert with expression


Details
-------
Delta Merge Node Details
---------------


Insert, delete and update data using the Delta merge command.



Parameters to be set:
+++++++++++++++

General Tab:


* OUTPUT STORAGE LEVEL: Choose how the data should be stored (e.g., DEFAULT, DISK_ONLY).
* TARGET PATH: Specify the directory where the Delta Lake table is located. Use the "Browse" button to navigate and select the location.
* SOURCE ALIAS: Provide an alias for the source DataFrame (e.g., "source"). This alias will be used in the merge condition.
* TARGET ALIAS: Provide an alias for the target Delta Lake table (e.g., "target"). This alias will be used in the merge condition.
* MERGE CONDITION: Specify the condition used to match rows between the source DataFrame and the target Delta Lake table. This condition is a SQL expression that typically involves comparing columns from the source and target.

When Matched Update Tab:


* Update Columns: Specify which columns in the target table should be updated based on matching conditions. Define the mappings between source and target columns.

When Matched Delete Tab:


* Delete Condition: Define the condition for deleting records from the target table. Records satisfying this condition will be deleted.

When Not Matched Tab:


* Insert Columns: Specify which columns should be inserted into the target table when no match is found. Define the mappings for the inserted values.


Examples
-------
Delta Merge Node Examples
---------------



Example of Merging Data into a Delta Lake Table
+++++++++++++++

General Tab:


* OUTPUT STORAGE LEVEL: DEFAULT
* TARGET PATH: /user/hive/warehouse/my_delta_table
* SOURCE ALIAS: source
* TARGET ALIAS: target
* MERGE CONDITION: source.customer_id = target.customer_id

When Matched Update Tab:


* Update Columns: target.name = source.name, target.age = source.age

When Matched Delete Tab:


* Delete Condition: source.status = 'inactive'

When Not Matched Tab:


* Insert Columns: (customer_id, name, age, status)
* Values to Insert: (source.customer_id, source.name, source.age, 'new')

This configuration would merge data from the source DataFrame (source) into the Delta Lake table located at /user/hive/warehouse/my_delta_table (target). Matching rows update name and age, inactive rows are deleted, and new rows are inserted with the specified columns and values.
