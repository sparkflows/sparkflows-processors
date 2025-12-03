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
        - A set of objects seperated by semicolon used for comparison..
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
===============
Expect Column Values To Be In Set Details
---------------


This feature allows users to validate that column values in a DataFrame are within a specified set of values. It helps ensure data quality by restricting column values to predefined acceptable options.



Input
+++++++++++++++


Column Name: Select the column that needs to be validated. The column type should match the expected data type.

Values: Enter the set of values that are acceptable for the selected column.

Mostly: Specifies the minimum percentage (0.0 - 1.0) of rows that must meet the condition for it to pass validation.


Output
+++++++++++++++


A DataFrame with validation results, indicating whether each row's value in the specified column is within the acceptable set.

The validation status can be used to filter or further process data based on quality checks.


Examples
===============
Example: If a column named "Status" in the DataFrame is expected to contain only "Approved," "Pending," or "Rejected," set the Values field to ["Approved", "Pending", "Rejected"]. This configuration ensures that any other value in the "Status" column will be flagged for review.
