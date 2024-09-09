String Functions
=========== 

String Functions Multiple

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeStringFunctionsMultiple

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - description
        - Description
        - Description
      * - inputCols
        - Columns
        - Columns
      * - functions
        - Function
        - String Function to apply
      * - replaceExistingCols
        - Replace Existing Cols
        - Whether to replace the existing columns or create new ones


Details
-------


String Functions Multiple Node Details
+++++++++++++++

This node creates a new Dataframe by transforming data of multiple columns using specified string functions. Multiple columns can be selected for transformations. Only one String Function can be selected for each transformation.

It applies String Function to on Columns to generate a new evaluated column.

Choose whether you want to replace(true) the existing column or create a new column(false) by choosing the value for the field `replaceExistingCols` .

Then the output dataframe will be created with the new column.

One can choose a column from the dropdown in the field `inputCols`, and then choose one of the function (trim, upper, lower, lefttrim, righttrim, removewhitespace) to apply to the column chosen.

Column data would be transformed as below based on the function selected:

Trim
```````````````

It removes leading and trailing blank spaces from values in the selected columns. -> 	Example:	'  Remove Spaces   ' would be changed to 'Remove Spaces'

Lower
```````````````

It changes case of the selected columns to lower in the output. -> 	Example:	'Change Case' would be changed to 'change case'
		
Upper
```````````````

It changes case of the selected columns to upper in the output. -> 	Example:	'Change Case' would be changed to 'CHANGE CASE'

LeftTrim
```````````````

It removes leading blank spaces from values in the selected columns. -> 	Example:	'  Remove Spaces   ' would be changed to 'Remove Spaces   '

RightTrim
```````````````

It removes trailing blank spaces from values in the selected columns. -> 	Example:	'  Remove Spaces   ' would be changed to '  Remove Spaces'

RemoveWhiteSpaces
```````````````

It removes all blank spaces from values in the selected columns. -> 	Example:	'  Remove Spaces   ' would be changed to 'RemoveSpaces'


Examples
-------


String Functions Multiple Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

EMP_CD    |    EMP_NAME    |    DEPT                   
-------------------------------------------------------
E01       |    DAVID       |    HUMAN RESOURCE         
E02       |    JOHN        |    PRODUCT SALES          
E03       |    MARK        |    MARKETING MANAGEMENT   

String Functions Multiple Node Configuration
```````````````

StringFunctionsMultiple node is configured as below to perform following transformations:

COLUMNS        |    FUNCTION          |      REPLACE EXISTING COLS 	
--------------------------------------------------------------------
EMP_NAME       |    lower             |      false
DEPT           |    removewhitespace  |      false

String Functions Multiple Node Output
```````````````

Outgoing Dataframe would be created as below after applying above transformations:

EMP_CD    |    EMP_NAME    |    DEPT                   |    EMP_NAME_lower    |    DEPT_removewhitespace             
-----------------------------------------------------------------------------------------------------------
E01       |    DAVID       |    HUMAN RESOURCE         |    david             |    HUMANRESOURCE
E02       |    JOHN        |    PRODUCT SALES          |    john              |    PRODUCTSALES
E03       |    MARK        |    MARKETING MANAGEMENT   |    mark              |    MARKETINGMANAGEMENT

Multiple transformations can be performed on a column; however, only the last transformation can have [REPLACE EXISTING COLS] option set as [true]
