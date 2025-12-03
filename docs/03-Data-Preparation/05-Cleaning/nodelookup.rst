Lookup
=========== 

Find values in a target column using a lookup table and either append fields or replace matched text.

Type
--------- 

pyspark2inputs

Class
--------- 

fire.nodes.etl.NodeLookup

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - Find
        - Find
        - 
      * - matchLocation
        - Match
        - How to match the lookup find value against the target text.
      * - targetCol
        - Find Within Field
        - Column in the input dataframe to search/modify.
      * - lookupFindCol
        - Find Value
        - Column in the lookup table that contains the find values.
      * - caseInsensitive
        - Case Insensitive
        - Perform case-insensitive matching.
      * - wholeWord
        - Match Whole Word Only
        - Match Whole Word Only
      * - Replace
        - Replace
        - 
      * - actionType
        - Action
        - Choose Append to add lookup columns, or Replace to change matched text in the target column.
      * - lookupReplaceCol
        - Lookup Replace Column
        - When Action is Replace: column in lookup table that contains the replacement text.
      * - appendCols
        - Append Columns
        - When Action is Append: which columns from the lookup table to append to the input rows.
      * - replaceMultipleItems
        - Replace Multiple Items
        - When replacing, replace all matches rather than only the first.


Details
-------
Lookup Node Details
===============

The Lookup node performs text-based lookups from a small reference (lookup) DataFrame against a target column in the main input DataFrame. It supports flexible matching options and can either append additional columns from the lookup row or replace matched text in the target column. The lookup DataFrame is broadcasted for efficient distributed processing, with a safety limit of 100,000 rows to prevent excessive memory usage.



General:
---------------



Match:
+++++++++++++++

Specifies how the find value matches the target text: 'Beginning of Field' (starts with), 'Any Part of Field' (contains), or 'Entire Field' (exact match).



Find Within Field:
+++++++++++++++

The column in the main input DataFrame to search or modify. This is a required field.



Find Value:
+++++++++++++++

The column in the lookup DataFrame containing the values to search for. This is a required field.



Case Insensitive:
+++++++++++++++

When enabled, matching ignores case differences (e.g., 'Apple' matches 'apple').



Match Whole Word Only:
+++++++++++++++

When enabled, matches are bounded by non-word characters (e.g., 'cat' matches 'The cat sat' but not 'category').



Replace Tab:
---------------



Action:
+++++++++++++++

Select 'Replace' to modify the target column by substituting matched text with replacement values from the lookup.



Lookup Replace Column:
+++++++++++++++

The column in the lookup DataFrame providing the replacement text for matches. Required when Action is Replace.



Replace Multiple Items:
+++++++++++++++

When enabled, all occurrences of the find value in the target are replaced; otherwise, only the first match is replaced.



Action:
+++++++++++++++

Select 'Append' to add columns from the matching lookup row to the input row without modifying the target.



Append Columns:
+++++++++++++++

The columns from the lookup DataFrame to add as new columns in the output. Required when Action is Append.



Output:
+++++++++++++++

The node outputs a single DataFrame:


For Append: Original schema plus the selected append columns (with nulls for non-matches).

For Replace: Original schema with the target column updated (unmatched rows unchanged).


Examples
-------
Lookup Node Examples
---------------



Replace Action Example
+++++++++++++++



Input:
+++++++++++++++


Main DataFrame (schema 0):


::

    | id | description |
    |----|----------------------|
    | 1 | I love red APPLE |
    | 2 | The quick brown fox |
    | 3 | Eating green apple pie |


Lookup DataFrame (schema 1):


::

    | find_term | replacement |
    |-----------|-------------|
    | APPLE     | fruit       |
    | fox       | animal      |

The Lookup node is configured as follows:


Match: Any Part of Field

Find Within Field: description

Find Value: find_term

Case Insensitive: true

Match Whole Word Only: true

Action: Replace

Lookup Replace Column: replacement

Replace Multiple Items: false



Output:
+++++++++++++++

::

    | id | description          |
    |----|----------------------|
    | 1  | I love red fruit     |
    | 2  | The quick brown animal |
    | 3  | Eating green apple pie |


(Row 1: 'APPLE' replaced with 'fruit'; Row 2: 'fox' replaced with 'animal'; Row 3: no match, unchanged.)



Append Action Example
+++++++++++++++



Input:
+++++++++++++++


Main DataFrame (schema 0):


::

    | id | category |
    |----|----------|
    | 1  | fruit    |
    | 2  | veggie   |
    | 3  | fruit    |


Lookup DataFrame (schema 1):


::

    | category | price | color  |
    |----------|-------|--------|
    | fruit    | 1.50  | red    |
    | veggie   | 2.00  | green  |


The Lookup node is configured as follows:


Match: Entire Field

Find Within Field: category

Find Value: category

Case Insensitive: false

Match Whole Word Only: false

Action: Append

Append Columns: [price, color]



Output:
+++++++++++++++

::

    | id | category | price | color |
    |----|----------|-------|-------|
    | 1  | fruit    | 1.50  | red   |
    | 2  | veggie   | 2.00  | green |
    | 3  | fruit    | 1.50  | red   |


(Rows 1 and 3 match 'fruit' and append price/color; Row 2 matches 'veggie' and appends its values.)
