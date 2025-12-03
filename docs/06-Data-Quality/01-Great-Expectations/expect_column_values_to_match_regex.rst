ExpectColumnValuesToMatchRegex
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnValuesToMatchRegex

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
      * - regex
        - Regex
        - regex to match
      * - mostly
        - Mostly
        - Mostly value is between 0 and 1, and evaluates it as a percentage and as long as mostly percent of rows evaluate to True, the expectation returns “success”: True.


Details
-------
Expect Column Values To Match Regex Details
---------------


This feature enables validation of column values in a DataFrame to ensure they match a specified regular expression (regex) pattern. It is useful for checking that values in a column adhere to a particular format or structure, such as an email or phone number format.



Input
+++++++++++++++


Column Name: Select the column that needs to be validated. The selected column should be of a type compatible with the regex pattern.

Regex: Enter the regular expression pattern that the column values should match.

Mostly: Specifies the minimum percentage (0.0 - 1.0) of rows that must meet the condition for the validation to pass.


Output
+++++++++++++++


A DataFrame with validation results, showing whether each row's value in the specified column matches the regex pattern.

This validation result can be used to identify rows that do not conform to the expected format for further review or correction.

Example: If a column named "Email" is expected to contain only valid email addresses, set the Regex field to a pattern like ^[\w\.-]+@[\w\.-]+\.\w{2,4}$. This configuration ensures that any invalid email addresses in the "Email" column will be flagged for further inspection.


Examples
-------
If an "ID" column is expected to contain only numbers with exactly 5 digits, setting the Regex field to ^\d{5}$ would result in the following outcomes for a sample DataFrame:


ID: 12345 - Pass (matches regex)

ID: 1234A - Fail (does not match regex)

ID: 67890 - Pass (matches regex)

ID: 5432 - Fail (does not match regex)

This setup helps ensure that only values matching the specified 5-digit format are present in the "ID" column.
