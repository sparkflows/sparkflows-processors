PatternMatch
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeCheckPattern

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Column Name
        - The column name.
      * - patterns
        - Patterns
        - Define matching patterns for column values.
      * - weightage
        - Weightage
        - Weightage


Details
-------
Pattern Match Node
---------------



Overview:
+++++++++++++++


The Pattern Match node allows you to match values in a specific column against predefined patterns. This is useful for filtering data based on regular expressions or specific string patterns.



Input:
+++++++++++++++


Column Name: The name of the column to check.

Patterns: A list of patterns to match against.


Output:
+++++++++++++++


The node will flag records where the specified column value matches any of the defined patterns.


Examples
-------
Example:
---------------


Let's assume we have a column named email and we want to identify invalid email addresses.


Configure the Node:


Column Name: email

Patterns: [^@]+@[^@]+\.[^@]+ (matches valid email addresses)


Node Execution:


Records with email values that do not match the pattern will be flagged.
