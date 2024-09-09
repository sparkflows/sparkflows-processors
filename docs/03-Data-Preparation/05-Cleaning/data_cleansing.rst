Data Cleansing
=========== 

This node cleanses the selected columns from the dataset

Input
--------------
It accepts DataFrame as input from the previous Node

Output
--------------
This node output cleansed data

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDataCleansing

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Columns
        - Columns
      * - inputCols
        - Select Columns
        - Columns to be processed for data cleansing
      * - Remove Nulls
        - Remove Nulls
      * - removeNullRows
        - Remove Null Rows
        - Remove Null Data. When no column is selected it removes row/column if all the fields are empty
      * - removeNullColumns
        - Remove Null Columns
        - Remove Null Data. When no column is selected it removes row/column if all the fields are empty
      * - Replace Nulls
        - Replace Nulls
      * - repalceWithBlanks
        - Replace With Blanks (String fields)
        - Replace Null Data
      * - replaceWithZero
        - Replace with 0 (Numeric fields)
        - Replace Null Data
      * - Remove Unwanted Characters
        - Remove Unwanted Characters
      * - allWhiteSpace
        - All Whitespace
        - Remove Unwanted Characters
      * - letters
        - Letters
        - Remove Unwanted Characters
      * - numbers
        - Numbers
        - Remove Unwanted Characters
      * - punctuation
        - Punctuation
        - Remove Unwanted Characters
      * - Modify Case
        - Modify Case
      * - modifyCase
        - Modify Case
        - Modify case to Upper,Lower or Title Case




