ExpectColumnValueToMatchStrftimeFormat
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValueToMatchStrftimeFormat

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - cols
        - Column Name
        - The column name.
      * - strftime_format
        - Strftime Format
        - A strftime format string to use for matching
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
-------
Expect Column Values Lengths to Equal
---------------


Expect the column entries to be strings with length equal to the provided value.



Keyword Args
+++++++++++++++


Column Name: The column name

strftime_format (str): A strftime format string to use for matching

Mostly (None or a float between 0 and 1): Return `success`: True if at least mostly fraction of values match the expectation.


Examples
-------
Example
---------------


Let's assume we have a column named date_of_birth with values like "1990-12-25", "12/25/1990", and "25-Dec-1990".


Configure the Node:


Column Name: date_of_birth

Strftime Format: %Y-%m-%d (for the first format)

Mostly: False (all values must match)

Node Execution:


The node will flag records with values like "12/25/1990" and "25-Dec-1990" as they don't match the specified format.
