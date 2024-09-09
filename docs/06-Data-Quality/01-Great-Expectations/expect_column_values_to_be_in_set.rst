ExpectColumnValuesToBeInSet
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToBeInSet

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
      * - values
        - values
        - A set of objects seperated by spaces used for comparison..
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
-------


Expect Column Values Lengths to Equal
+++++++++++++++

Expect the column entries to be strings with length equal to the provided value.

Keyword Args
```````````````

Column Name: The column name
Value (int or None): NodeExpectColumnValuesToBeInSet
Mostly (None or a float between 0 and 1): Return `success`: True if at least mostly fraction of values match the expectation.


