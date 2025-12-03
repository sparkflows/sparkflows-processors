Split Into Good And Bad Records
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeSplitIntoGoodAndBadRecords

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - uniqueId
        - Create Identifier Column
        - Enter name for a unique identifier column
      * - separator
        - Separator
        - Enter a separator for separating exception_reason and failed column name


Details
===============
Split Into Good And Bad Records Details
---------------


Lower numbered edge outputs the rows which passed the checks.

Higher numbered edge outputs the rows which failed the checks.


Examples
===============
Example:
---------------


Let's assume we have a DataFrame with a column is_valid that indicates whether a record is valid or not.


Configure the Node:


Create Identifier Column: True

Separator: "_"

Node Execution:


Records with is_valid = 1 will be routed to the "Good Records" output.

Records with is_valid = 0 will be routed to the "Bad Records" output.

A new column named "row_index_" will be added to both outputs to identify the original row number.
