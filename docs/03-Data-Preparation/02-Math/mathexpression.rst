Math Expression
=========== 

Creates new columns using the specified expressions

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeMathExpression

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCols
        - Output Column
        - Output Column Name
      * - expressions
        - Math Expression
        - Define math expression.


Details
-------


 Math Expression Details 
+++++++++++++++

This node creates a new DataFrame by adding new columns to the incoming Dataframe as per the specified expression.

New columns can be computed using existing columns in the Dataframe.

Following functions can be used in Expressions:

 Computations
```````````````

* 	Computation expression -> Example : LIST_PRICE + TAX_AMT - DISCOUNT


Math Functions
```````````````

* 	 abs :  Get the absolute value of an expression. Ex: abs(LIST_PRICE)
* 	 pow :  Raises expr1 to the power of expr2. Ex: pow(LIST_PRICE, 2)
* 	 cos :  Get the trigonometric cosine of an expression. Ex: cos(LIST_PRICE)


Valid examples of Math functions - abs, acros, asin, atan, atan2, bin, cbrt, ceil, conv, cos, sosh, exp, expm1, factorial, floor, hex, hypot, log, log10, log1p, log2, pmod, pow, rint, round, shiftLeft, shiftRight, shiftRightUnsigned, signum, sin, sinh, sqrt, tan, tanh, toDegrees, toRadians, unhex (single choice)


Examples
-------


Incoming Dataframe has following rows:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT
--------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0
P03       |    HAMMER            |    100.0         |    10.0       |    5.0

If MathExpression node is configured to compute a new column [NET_AMT] based on expression [LIST_PRICE + TAX_AMT - DISCOUNT]
then outgoing Dataframe would be created as below with new column added:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT    |    NET_AMT    
------------------------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0        |    1050.0
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0       |    1550.0
P03       |    HAMMER            |    100.0         |    10.0       |    5.0         |    105.0
