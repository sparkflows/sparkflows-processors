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
      * - n
        - Num Rows to Print
        - number of rows to be printed
      * - displayDataType
        - Display Data Type
        - If true display rows DataType


Details
-------


Print N Rows Node Details
+++++++++++++++

This node is used to print the first N rows from the incoming dataframe.

The Number of rows that needs to be printed can be configured in the node.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TITLE : Enter a short description for the type of information being displayed.
*  NUM ROWS TO PRINT : Set an integer value(N) which controls the number of rows to be displayed(Default N=10).
*  DISPLAY DATA TYPE : Shows the output dataframe column datatypes by default.


Output
```````````````

*  This node can be used to view, analyze and validate the output of the Dataframe.


