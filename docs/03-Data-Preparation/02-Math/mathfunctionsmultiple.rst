Math Functions
=========== 

Create new columns or replaces the existing ones by using the specified function

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeMathFunctionsMultiple

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
        - Math Function to apply
      * - replaceExistingCols
        - Replace Existing Cols
        - Replace Existing Columns (true, false)
      * - scales
        - Scale
        - Scale to be used when applying the Math Function


Details
-------


Math functions Details
+++++++++++++++

This node creates a new DataFrame by adding new columns to the incoming Dataframe using specified math functions.

One can choose a column from the dropdown in the field `inputCols`, and then choose one of the function (log, sqrt, pow, exp, round) to apply to the column chosen.

Choose whether you want to replace(true) the existing column or create a new column(false) by choosing the value for the field `replaceExistingCols` .

Then the output dataframe will be created with the new column.

Examples:
```````````````

* 	 log :  To get the natural logarithm (base e). Ex: log(LIST_PRICE)
* 	 sqrt :  To get the positive square root. Ex: sqrt(LIST_PRICE)
* 	 pow :  Raises expr1 to the power of expr2. Ex: pow(LIST_PRICE, 2)
* 	 exp :  Returns e to the power of expr. Ex: exp(LIST_PRICE)
*   round: Rounds the column value to the nearest intege. Ex: round(LIST_PRICE,2)


Examples
-------


Incoming Dataframe has following rows:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT
--------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0
P03       |    HAMMER            |    100.0         |    10.0       |    5.0

If MathFuntion node is configured to compute a new column [SQRT_AMT] based on function SQRT of `TAX_AMT` column
then outgoing Dataframe would be created as below with new column added:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT    |    SQRT_AMT
------------------------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0        |    10.0
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0       |    14.14
P03       |    HAMMER            |    100.0         |    10.0       |    5.0         |    3.16
