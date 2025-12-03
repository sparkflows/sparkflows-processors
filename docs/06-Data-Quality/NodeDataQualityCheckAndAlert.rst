NodeDataQualityCheckAndAlert
=========== 

This node is used to perform data quality checks on a DataFrame and send alerts based on the results.

Type
--------- 

transform

Class
--------- 

fire.nodes.quality.NodeDataQualityCheckAndAlert

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - emailAddress
        - Email Address
        - Email Address. Add multiple email in comma separated
      * - subject
        - Subject
        - The subject of the alert email.
      * - threshold
        - Threshold
        - The minimum acceptable overall data quality score (0-100). An alert is sent if the score is less than or equal to this threshold.
      * - dataQualityResultPath
        - Result Path
        - The path to save the good and bad records


Details
-------
NodeDataQualityCheckAndAlert
---------------



Overview:
+++++++++++++++


This node is used to perform data quality checks on a DataFrame and send alerts based on the results. It allows you to define various checks, such as:


Missing values: Checks for null or empty values in columns.

Invalid data types: Ensures that data in each column conforms to the expected data type.

Outliers: Identifies values that deviate significantly from the norm.

Duplicate values: Detects duplicate records.

Custom checks: Allows you to define custom checks using expressions.



Input:
+++++++++++++++


Email Address: The email address to send alerts to.

Threshold: The percentage of records that must fail a check to trigger an alert.

Result Path: The path to save the detailed report of the data quality checks.


Output:
+++++++++++++++


The node will send an email alert if the threshold is exceeded and save a detailed report of the checks to the specified path.


Examples
-------
Example:


Let's say you want to check for missing values and invalid data types in a DataFrame.


Configure the Node:


Email Address: [email address removed]

Threshold: 10 (10% of records must fail)

Result Path: /path/to/report.csv

Node Execution:


The node will check for missing values and invalid data types in each column.

If more than 10% of records fail any check, an email alert will be sent.

A detailed report of the checks will be saved to the specified path.
