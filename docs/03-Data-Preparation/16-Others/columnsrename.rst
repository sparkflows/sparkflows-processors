Columns Rename
=========== 

This node creates a new DataFrame by renaming existing columns with the new name

Input
--------------
This type of node takes in a DataFrame and transforms it to another DataFrame.

Output
--------------
The specified columns are renamed to have the new names.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeColumnsRename

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - currentColNames
        - Current Column Names
        - Current Column Names
      * - newColNames
        - Columns New Name
        - New name for existing columns
      * - bulkColumnRename
        - BulkColumnRename
        - 
      * - bulkType
        - Type
        - Select Type
      * - prefix
        - Prefix
        - Prefix Value
      * - suffix
        - Suffix
        - Suffix Value
      * - remove_extra_charcter
        - Extra Charcter
        - extra_charcter
      * - replace_pattern
        - Replace Pattern
        - regex replace pattern to search
      * - with_pattern_replacement
        - With Pattern Replacement
        - regex replacement for matched pattern in Replace Pattern
      * - replace
        - Replace
        - replace pattern to search
      * - with_replacement
        - Replacement
        - replacement for matched replace
      * - inputCols
        - Current Column Names
        - Current Column Names
      * - inputColumnPropagation
        - Enable Input Column Propagation
        - When enabled, automatically include all unspecified input columns.


Details
-------
This node creates a new DataFrame by renaming existing columns with the new name.


For the columns to be renamed, provide the new column name. The output dataframe would have the specified columns renamed to the new ones.


Examples
-------
If incoming Dataframe has a column as [CUST NAME] that needs to be renamed to [CUST_NAME] then below details need to be provided in the node:



* CURRENT COLUMN NAMES : CUST NAME
* COLUMNS NEW NAME : CUST_NAME


This would result in output Dataframe having renameed column [CUST_NAME]. A seprate row needs to be added for each Column Rename requirement.
