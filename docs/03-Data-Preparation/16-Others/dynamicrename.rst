Dynamic Rename
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

pyspark2inputs

Class
--------- 

fire.nodes.etl.NodeDynamicRename

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
        - Rename Mode
        - Select Type
      * - prefix
        - Add Prefix
        - Prefix Value
      * - suffix
        - Add Suffix
        - Suffix Value
      * - remove_prefix
        - Remove Prefix
        - Prefix Value
      * - remove_suffix
        - Remove Suffix
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
      * - inputMode
        - Use Positional Rename
        - Reassign based on row position instead of mapping
      * - oldFieldNameCol
        - Old Field Name from Column
        - Select from list of Right input field names . For Positional Rename, leave this empty if 'Use Positional Rename' is True.
      * - newFieldNameCol
        - New Field Name from Column
        - Select from list of Right input field names
      * - inputCols
        - Columns To Rename
        - Columns To Rename
      * - inputColumnPropagation
        - Enable All Columns To Rename
        - Enable All Columns To Rename
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Output Columns Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats




