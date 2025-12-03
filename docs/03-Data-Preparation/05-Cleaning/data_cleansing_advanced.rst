Data Cleansing Advanced
=========== 

This node cleanses the selected columns from the dataset

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
This node outputs cleansed data

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDataCleansingAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Remove Nulls
        - Remove Nulls
        - 
      * - removeNullRows
        - Remove Null Rows
        - Removes rows with null values in any selected column; removes all rows if no columns are selected
      * - nullRowsCols
        - Columns for Null Rows Check
        - Select columns to apply Remove Null Rows operation
      * - removeNullColumns
        - Remove Null Columns
        - Removes columns with all null values; removes selected columns with at least one null if columns are specified
      * - nullColsCols
        - Columns for Null Columns Check
        - Select columns to apply Remove Null Columns operation
      * - Column Wise
        - Column-Level Cleansing
        - 
      * - inputCols
        - Input Columns
        - Select columns to be processed for data cleansing
      * - replaceWithBlanks
        - Replace Nulls With Blanks (String Fields)
        - Replaces null values in string fields with empty strings ('') for the corresponding selected column
      * - replaceWithZero
        - Replace Nulls With 0 (Numeric Fields)
        - Replaces null values in numeric fields with 0 for the corresponding selected column
      * - removeWhitespaces
        - Remove Whitespaces
        - Removes whitespace characters from the corresponding selected columns
      * - removeLetters
        - Remove Letters
        - Removes alphabetic characters from the corresponding selected columns
      * - removeDigits
        - Remove Digits
        - Removes numeric digits from the corresponding selected columns
      * - removeSigns
        - Remove Special Signs
        - Removes special symbols or signs from the corresponding selected columns
      * - removeCommas
        - Remove Commas
        - Removes commas from the corresponding selected columns
      * - modifyCases
        - Modify Case
        - Converts text in the corresponding selected columns to upper, lower, or title case


Details
===============
Data Cleansing Advanced – Enterprise-Grade Column-Level Cleaning
---------------


This is the professional version of Data Cleansing – giving you full per-column control instead of global rules. Used by data engineers building mission-critical, auditable, high-volume pipelines where every field has its own exact requirement.



When to Use Advanced vs Regular
+++++++++++++++


* Use Regular → 80% of cases (same rule for many columns)
* Use Advanced → when you need different treatment per column (this node!)


Real Enterprise Scenarios
+++++++++++++++

* phone_number → remove everything except digits
* email → lower case + trim
* revenue → null → 0
* customer_name → title case + trim
* product_code → upper case + remove spaces
* address_line → remove line breaks only


Pro Tips
+++++++++++++++

* Always place this node right after Read/Union
* Combine with “Select” afterward to reorder/drop temp columns
* Use the regular Data Cleansing node first for global fixes, then Advanced for exceptions


Examples
===============
Data Cleansing Advanced – Real-World Column-Specific Rules
---------------



Example 1 – Standard Customer Master Cleanse
+++++++++++++++

::

    | Column          | Rules Applied                                      | Before                     | After                  |
    |-----------------|----------------------------------------------------|----------------------------|------------------------|
    | customer_id     | (none)                                             |                            |                        |
    | full_name       | Title Case + Trim + Remove Duplicate Spaces       | "  john   DOE  "           | "John Doe"             |
    | email           | Lower Case + Trim                                  | "  John.Doe@Company.COM\\n"| "john.doe@company.com" |
    | phone           | Remove Letters + Remove Special Signs + Remove Whitespaces | "(555) 123-4567  "    | "5551234567"           |
    | revenue_ytd     | Replace Null → 0                                   | null                       | 0                      |
    | join_date       | (none)                                             |                            |                        |



Example 2 – Mixed Financial Data
+++++++++++++++

::

    | Column          | Rules                                              | Result                        |
    |-----------------|----------------------------------------------------|-------------------------------|
    | amount_usd      | Replace Null → 0 + Remove Commas                   | "1,250.00" → 1250.00          |
    | currency        | Upper Case + Trim                                  | "usd" → "USD"                 |
    | description     | Remove Tabs/Line Breaks only                       | "Line1\\nLine2" → "Line1 Line2"|



Example 3 – Product Catalog Standardization
+++++++++++++++

::

    | Column          | Rules                                              | Before                     | After                  |
    |-----------------|----------------------------------------------------|----------------------------|------------------------|
    | sku             | Upper Case + Remove Whitespaces + Remove Signs     | "abc-123 xyz"              | "ABC123"               |
    | product_name    | Title Case + Trim                                  | "wireless mouse"           | "Wireless Mouse"       |
    | price           | Replace Null → 0                                   | null                       | 0                      |



Example 4 – Remove Null Rows Only on Key Fields
+++++++++++++++


* nullRowsCols: customer_id, email

→ Any row missing either of these is dropped (keeps dirty rows that only miss optional fields)



Example 5 – Aggressive Garbage Cleanup
+++++++++++++++

::

    | Column          | Rules                                              |
    |-----------------|----------------------------------------------------|
    | legacy_id       | Remove Letters + Remove Signs → keep only digits  |
    | notes           | Remove all Digits + Remove Special Signs          |
