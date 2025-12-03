ExpectColumnValueLengthsToEqual
===========



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValueLengthsToEqual

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
      * - value
        - value
        - The expected value for a column entry length.
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
-------
Expect Column Values Lengths to Equal
+++++++++++++++


Expect the column entries to be strings with length equal to the provided value.



Keyword Args
+++++++++++++++


Column Name: The column name

Value (int or None): The expected value for a column entry length.

Mostly (None or a float between 0 and 1): Return `success`: True if at least mostly fraction of values match the expectation.


Examples
-------
Expect Column Value Lengths to Equal Node Examples
+++++++++++++++

Scenario: You have a dataset with columns column6 and column7 containing string values, and you want to ensure all entries in these columns are exactly 5 characters long.


Configuration:


Column Name: column6

Value: 5

Mostly: 100%

Outcome:


If any value in column6 is not exactly 5 characters, it will be flagged, and discrepancies will be listed in the output.

Scenario: You want to check if the numeric columns column1 to column5 have consistent integer values without any floating-point numbers in column2.


Configuration:


Column Name: column2

Mostly: 100%

Outcome:


Any non-integer values in column2 will be flagged, ensuring data type consistency across integer and double columns.
