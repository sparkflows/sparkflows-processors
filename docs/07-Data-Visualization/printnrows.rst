Print N Rows
=========== 

Prints the specified number of records in the DataFrame. It is useful for seeing intermediate output

Type
--------- 

transform

Class
--------- 

fire.nodes.util.NodePrintFirstNRows

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - title
        - Title
        - 
      * - n
        - Num Rows to Print
        - Number of rows to be printed
      * - columns
        - Select Columns to Print
        - Select the columns to display, or leave blank to show all columns
      * - enableInExecution
        - Enable in Execution
        - If it's enabled, during the execution data is displayed.
      * - displayDataType
        - Display Data Type
        - If true display rows DataType


Details
-------
Print N Rows Node Details
---------------


This node is used to print the first N rows from the incoming dataframe. You can choose to display all columns or select specific columns to focus on relevant data.



Input Parameters
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* TITLE : Enter a short description for the type of information being displayed.
* NUM ROWS TO PRINT : Set an integer value(N) which controls the number of rows to be displayed (Default N=10).
* SELECT COLUMNS TO PRINT : Choose specific columns to display. If no columns are selected, all columns will be shown.
* DISPLAY DATA TYPE : Shows the output dataframe column datatypes by default.


Output
+++++++++++++++

* Displays the first N rows of the DataFrame with selected columns
* Passes the filtered DataFrame (with selected columns) to subsequent nodes
* Useful for data validation, debugging, and intermediate result inspection


Examples
-------
Example 1: Display All Columns (No Column Selection)
+++++++++++++++

When input 5 in "Num Rows to Print" and no columns selected, it shows first 5 rows with all columns:


PartID    SupplierID    PartName    Category    Price

P9271    S798    Part_D    Electronics    249.99

P523    S955    Part_K    Mechanical    156.50

P3201    S332    Part_M    Electronics    320.75

P9634    S527    Part_G    Mechanical    89.99

P9345    S850    Part_M    Electronics    275.00



Example 2: Display Selected Columns Only
+++++++++++++++

When input 5 in "Num Rows to Print" and columns PartID, PartName, Price are selected:


PartID    PartName    Price

P9271    Part_D    249.99

P523    Part_K    156.50

P3201    Part_M    320.75

P9634    Part_G    89.99

P9345    Part_M    275.00



Example 3: With Data Types Displayed
+++++++++++++++

When "Display Data Type" is enabled:


Column    DataType

PartID    string

PartName    string

Price    double


PartID    PartName    Price

P9271    Part_D    249.99

P523    Part_K    156.50

P3201    Part_M    320.75
