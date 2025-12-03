Data Cleansing
=========== 

One-stop data quality powerhouse – instantly clean dozens of common messy data issues: null handling, whitespace, unwanted characters, case standardization, and more. Perfect for preparing raw source data (CSV, Excel, APIs, logs) before analytics, modeling, or reporting.

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
        - 
      * - inputCols
        - Select Columns
        - Columns you want to clean. Leave empty to apply settings globally where it makes sense (e.g., trim whitespace on all string columns).
      * - Remove Nulls
        - Remove Nulls
        - 
      * - removeNullRows
        - Remove Null Rows
        - Drop entire rows that contain nulls in the selected columns (or any column if none selected). Great for strict data quality requirements.
      * - removeNullColumns
        - Remove Null Columns
        - Drop entire columns that are completely null/empty. Useful after Union when some sources don’t have certain fields.
      * - Replace Nulls
        - Replace Nulls
        - 
      * - replaceWithBlanks
        - Replace Nulls → Blank (String fields)
        - Replace nulls in string columns with empty string '' instead of literal 'null'. Makes downstream joins and reports look clean.
      * - replaceWithZero
        - Replace Nulls → 0 (Numeric fields)
        - Replace nulls in numeric columns with 0. Essential for aggregations (sum, avg) so nulls don’t skew results.
      * - Remove Unwanted Characters
        - Remove Unwanted Characters
        - 
      * - trimWhitespace
        - Trim Leading/Trailing Whitespace
        - Remove spaces before/after text (e.g., ' John ' → 'John'). The #1 most common data issue!
      * - removeTabsLineBreaks
        - Remove Tabs, Line Breaks & Duplicate Spaces
        - Clean up copy-paste mess: replaces \t, , \r and multiple spaces with single space.
      * - allWhiteSpace
        - All Whitespace Characters
        - Remove every kind of whitespace (including non-breaking spaces).
      * - letters
        - Letters (A-Z, a-z)
        - Strip all letters – useful for extracting numbers from mixed fields.
      * - lettersExceptions
        - Letters Exceptions
        - Comma-separated letters to KEEP (e.g., 'A,E,I,O,U' to keep vowels).
      * - numbers
        - Numbers (0-9)
        - Strip all digits – perfect for cleaning names that contain numbers.
      * - numbersExceptions
        - Numbers Exceptions
        - Digits to KEEP (e.g., '123' to preserve house numbers).
      * - punctuation
        - Punctuation & Symbols
        - Remove !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~ etc.
      * - punctuationExceptions
        - Punctuation Exceptions
        - Symbols to KEEP (e.g., '.,-' for decimal numbers and names like O'Connor).
      * - Modify Case
        - Modify Case
        - 
      * - modifyCase
        - Modify Case
        - Standardize text case: • Upper case → JOHN DOE • Lower Case → john doe • Title Case → John Doe • Default → no change


Details
===============
Data Cleansing Node – Fix 95% of Real-World Data Mess in One Click
---------------


The Data Cleansing node is the fastest way to turn dirty, inconsistent source data into clean, trusted, analysis-ready tables. Used by thousands of analysts daily to eliminate the most common (and frustrating) data quality issues instantly.



Real-World Problems It Solves Instantly
+++++++++++++++


* CSV/Excel files with extra spaces, tabs, line breaks
* Nulls showing as blank, “null”, or actual null → breaking sums
* Mixed case names/emails (JoHn.DoE@company.com)
* Phone numbers with (123) 456-7890 → - → spaces
* Product codes with hidden characters
* Copied data from PDFs/websites with garbage symbols


Best Practice Combinations
+++++++++++++++


1. Standard Clean Profile (most common):


* Select all string columns
* Trim Whitespace: true
* Remove Tabs/Line Breaks: true
* Replace Nulls → Blank: true
* Title Case


2. Phone/Email Clean:


* Remove Punctuation (except @ and .)
* Trim + Lower Case


3. Numeric Clean:


* Replace Nulls → 0
* Remove Letters + Punctuation


Pro Tips
+++++++++++++++

* Run this node right after any Read/Union node
* Combine with “Select” node after to drop/reorder
* Use “Remove Null Columns” after Union Advanced to clean up schema drift


Examples
===============
Data Cleansing – Before & After Real Examples
---------------



Example 1 – Typical Messy Customer Import
+++++++++++++++

::

    | Raw Data                          | After Standard Clean Profile |
    |-----------------------------------|------------------------------|
    | "  john DOE  "                    | "John Doe"                   |
    | null                              | "" (blank)                   |
    | "jane.smith@Company.com\\n"        | "Jane Smith" / "jane.smith@company.com" |
    | "O'Connor, Patrick"               | "O'Connor, Patrick" (preserves ' and ,) |
    | "123-456-7890  "                  | "1234567890"                 |



Example 2 – Financial Data with Nulls
+++++++++++++++

::

    | amount_raw | → Replace Null → 0 + Trim |
    |------------|---------------------------|
    | null       | 0                         |
    | "  1,250.00   " | "1250.00"            |



Example 3 – Product Codes with Garbage
+++++++++++++++

::

    | raw_code                  | Remove Letters + Punctuation |
    |---------------------------|------------------------------|
    | "ABC-123!@#XYZ"           | "123"                        |
    | "SKU_456  \t\\n"           | "456"                        |



Example 4 – Email Standardization
+++++++++++++++

::

    | raw_email                     | Lower Case + Trim + Remove Tabs |
    |-------------------------------|---------------------------------|
    | "  John.Doe@Company.COM  \\n"  | "john.doe@company.com"          |



Example 5 – Name Consistency for Matching
+++++++++++++++

::

    | raw_name              | Title Case + Trim + Remove Duplicate Spaces |
    |-----------------------|---------------------------------------------|
    | "  john   doe "       | "John Doe"                                  |
    | "MARY-ANNE SMITH"     | "Mary-Anne Smith"                           |
