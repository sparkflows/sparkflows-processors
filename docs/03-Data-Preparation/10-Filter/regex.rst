Regex Advanced
===========

Advanced regex operations for text processing - similar to Alteryx Regex Tool with auto-detection of capturing groups

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
Returns a DataFrame with extracted patterns, marked matches, replaced text, or tokenized data based on the selected regex mode

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRegexAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - general
        - General
        - 
      * - inputCol
        - Input Column
        - Column to apply regex operations on
      * - regexPattern
        - Regular Expression Pattern
        - Enter the regex pattern
      * - regexMode
        - Regex Mode
        - Select the regex operation mode
      * - caseSensitive
        - Case Sensitive
        - Enable case-sensitive pattern matching
      * - errorHandling
        - Error Handling
        - How to handle errors: FAIL (stop execution), SKIP (remove row), IGNORE
      * - replacementText
        - Replacement Text
        - Text to replace matched patterns with (REPLACE mode only)
      * - tokenSplit
        - Split to Columns
        - Enter Number of columns to split
      * - inputMatchCol
        - Match Column Name
        - Enter Column Name for Match Status
      * - newColName
        - Target Column
        - Enter New Column Name
      * - regularexpression
        - Expression
        - Regular Expression on how to get the data which has to be placed under this column
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


Details
-------
Regex Advanced Node
+++++++++++++++



Overview:
+++++++++++++++


The Regex Advanced node provides powerful text processing capabilities using regular expressions, similar to the Alteryx Regex Tool. It allows parsing, tokenizing, matching, and replacing text in a DataFrame column. Users can also auto-detect capturing groups for parsing operations and control case-sensitivity and error handling.



Input:
+++++++++++++++



* Input Column: The column from the input DataFrame on which regex operations will be applied.

* Regex Pattern: The regular expression pattern to extract, match, replace, or tokenize text.

* Regex Mode: Select the operation mode:

* **PARSE** – Extract data into new columns based on capturing groups.
* **TOKENIZE_COL** – Split text into multiple columns.
* **TOKENIZE_ROW** – Split text into multiple rows.
* **REPLACE** – Replace matched patterns with specified text.
* **MATCH** – Create a column marking whether the pattern matches.

* Case Sensitivity: Specify whether pattern matching should be case-sensitive.

* Error Handling: Choose how errors should be handled – FAIL, SKIP, or IGNORE.


Output:
+++++++++++++++



Returns a transformed DataFrame with new columns or updated values based on the selected regex mode. Output may include:



* Parsed columns from capturing groups (PARSE mode).
* Tokenized columns or rows (TOKENIZE_COL/TOKENIZE_ROW).
* Replaced text in the input column (REPLACE mode).
* Match status column indicating success/failure (MATCH mode).


Advanced Options:
+++++++++++++++


* Replacement Text: Text to replace matches (REPLACE mode).
* Split to Columns: Number of columns to split text into (TOKENIZE_COL mode).
* Match Column Name: Name of the column storing match status (MATCH mode).
* Target Column Names & Expressions (Parse tab): Map capturing groups to new column names with corresponding regex expressions.
* Infer Schema (Schema tab): Define output column names, types, and formats.


Examples
-------
Regex Advanced Node Examples
+++++++++++++++



Example 1 – Parse Mode
+++++++++++++++



* *Input DataFrame:**

::

    | id | info                |
    | -- | ------------------- |
    | 1  | Name: John Age: 25  |
    | 2  | Name: Alice Age: 30 |
    | 3  | Name: Bob Age: 22   |


* *Node Configuration:**

* Input Column: info
* Regex Pattern: `Name:\s*(\w+)\s+Age:\s*(\d+)`
* Regex Mode: PARSE
* Target Column Names: ["name", "age"]
* Expressions: ["(\w+)", "(\d+)"]

* *Output DataFrame:**

::

    | id | info                | name  | age |
    | -- | ------------------- | ----- | --- |
    | 1  | Name: John Age: 25  | John  | 25  |
    | 2  | Name: Alice Age: 30 | Alice | 30  |
    | 3  | Name: Bob Age: 22   | Bob   | 22  |




Example 2 – Replace Mode
+++++++++++++++


* *Input DataFrame:**

::

    | id | email                                                 |
    | -- | ----------------------------------------------------- |
    | 1  | [john.doe@gmail.com](mailto:john.doe@gmail.com)       |
    | 2  | [alice.smith@yahoo.com](mailto:alice.smith@yahoo.com) |


* *Node Configuration:**

* Input Column: email
* Regex Pattern: `@.*`
* Regex Mode: REPLACE
* Replacement Text: `@example.com`

* *Output DataFrame:**

::

    | id | email                                                     |
    | -- | --------------------------------------------------------- |
    | 1  | [john.doe@example.com](mailto:john.doe@example.com)       |
    | 2  | [alice.smith@example.com](mailto:alice.smith@example.com) |




Example 3 – Match Mode
+++++++++++++++


* *Input DataFrame:**

::

    | id | code  |
    | -- | ----- |
    | 1  | AB123 |
    | 2  | XY789 |
    | 3  | 1234  |


* *Node Configuration:**

* Input Column: code
* Regex Pattern: `^[A-Z]{2}\d{3}$`
* Regex Mode: MATCH
* Match Column Name: is_valid

* *Output DataFrame:**

::

    | id | code  | is_valid |
    | -- | ----- | -------- |
    | 1  | AB123 | true     |
    | 2  | XY789 | true     |
    | 3  | 1234  | false    |
