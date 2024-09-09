Expressions
=========== 

This node creates a new DataFrame by adding new columns to the incoming Dataframe as per the Expression computation

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeExpressions

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
        - Description to capture processing in this node
      * - outputCols
        - New Column Names
        - New Column Names
      * - expressions
        - Expressions
        - Expressions to create new columns


Details
-------


Expressions Node Details
+++++++++++++++

This node creates a new DataFrame by adding new columns to the incoming Dataframe as per the expressions computated.

It computes expressions to calculate the value of a metric column based on mathematical or logical operations performed on other metric columns.

New column can also be computed using existing columns in the Dataframe.

Following functions can be used in Expressions:
###############

 Mathematical Computations
###############


* 	Maths Operations -> Example : LIST_PRICE + TAX_AMT - DISCOUNT
* 	Maths Operations -> Example : DISCOUNT / LIST_PRICE
* 	Maths Operations -> Example : (DISCOUNT / LIST_PRICE) * 100


String Functions
###############


* 	Concatenation     -> Example : CONCAT(PRD_CD,':',PRD_NAME)
* 	Substring     -> Example : SUBSTR(PRD_NAME,1,3)
* 	Replace		 	-> Example : REPLACE(PRD_NAME,'M','$')
* 	Right		 	-> Example : RIGHT(PRD_NAME, 5)
* 	Left		 	-> Example : LEFT(PRD_NAME, 5)
* 	Right Trim	 	-> Example : RTRIM(PRD_NAME)
* 	Intial Caps	 	-> Example : INITCAP(LOWER(PRD_NAME))
* 	Length		 	-> Example : LENGTH(PRD_NAME)
* 	Split		 	-> Example : SPLIT(PRD_NAME, ' ')


Number Format Functions
###############


* 	Format Number	-> Example : FORMAT_NUMBER(LIST_PRICE, '#,###,###,###.00')


Date and Timestamp Functions
###############

Fetch Current Date and Time
```````````````


* 	Current Date value				          -> Example : CURRENT_DATE
* 	Current Date Time value				      -> Example : CURRENT_TIMESTAMP


Format Date-Time values
```````````````

* 	Date Format						            	-> Example : DATE_FORMAT(CURRENT_DATE, 'MMM dd, yyyy')
* 	Date-Time Format						            	-> Example : DATE_FORMAT(CURRENT_DATE, 'MMM dd, yyyy hh:mm:ss')


String to Date-Time conversion
```````````````

* 	Convert a String to Date	      		-> Example : TO_DATE('12-DEC-21', 'dd-MMM-yy')
* 	Convert a String to Datetime						            	-> TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS')


Date-Time addition and substraction
```````````````

* 	Add/Substract Years to a Date		  -> Example : ADD_MONTHS(CURRENT_DATE, 12)
* 	Add/Substract Months to a Date		  -> Example : ADD_MONTHS(CURRENT_DATE, 3)
* 	Add/Substract Days to a Date		    -> Example : DATE_ADD(CURRENT_DATE, -1)
* 	Add/Substract Hours to a Date		  -> Example : TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS') + Interval 2 Hours
* 	Add/Substract Minutes to a Date		  -> Example : TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS') + Interval 2 Minutes
* 	Add/Substract Seconds to a Date		  -> Example : TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS') + Interval 2 Seconds
* 	Add/Substract Hours and Minutes to a Date		  -> Example : TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS') + Interval 2 Hours + Interval 2 Minutes
* 	Substract Hours and Minutes from a Date		  -> Example : TO_TIMESTAMP('12-DEC-21 15:55:45:789', 'dd-MMM-yy HH:mm:ss:SSS') - Interval 2 Hours - Interval 2 Minutes


Fetch Next Day and Last Day of Month
```````````````

* 	Last Day of a Month   				      -> Example : LAST_DAY(CURRENT_DATE)
* 	Next Day value		   				        -> Example : NEXT_DAY(CURRENT_DATE, 'Sunday')
* 	First Day of Year/Month				      -> Example : DATE_TRUNC('MONTH', CURRENT_DATE)
* 	Year/Month/Quarter/DayOfMonth value	-> Example : YEAR(CURRENT_DATE)/MONTH(CURRENT_DATE)/QUARTER(CURRENT_DATE)/DAYOFMONTH(CURRENT_DATE)/DAYOFWEEK(CURRENT_DATE)
* 	Day/Week count of the Year			    -> Example : DAYOFWEEK(CURRENT_DATE)/WEEKOFYEAR(CURRENT_DATE)


Date Difference functions
```````````````

* 	Date Diff between two Dates			    -> Example : DATEDIFF(CURRENT_DATE, TO_DATE('12-DEC-21', 'dd-MMM-yy'))
* 	Number of Months between two Dates	-> Example : MONTHS_BETWEEN(CURRENT_DATE, TO_DATE('12-DEC-21', 'dd-MMM-yy'))
* 	Number of Years between two Dates	-> Example : MONTHS_BETWEEN(CURRENT_DATE, TO_DATE('12-DEC-21', 'dd-MMM-yy')) / 12


Regex Functions
###############


* 	Replace using Regex		-> Example : REGEXP_REPLACE(PRD_NAME, 'E', '#')


Examples
-------


Expressions Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT
--------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0
P03       |    HAMMER            |    100.0         |    10.0       |    5.0

Expressions Node Configuration
```````````````

Expressions node is configured to compute new columns as below:

NEW COLUMNS NAME         |    EXPRESSIONS
-----------------------------------------------------------------
NET_AMT                  |    LIST_PRICE + TAX_AMT - DISCOUNT
PRD_DETAILS              |    CONCAT(PRD_CD,':',PRD_NAME)

Node Output
```````````````

Outgoing Dataframe would be created as below with new columns added:

PRD_CD    |    PRD_NAME          |    LIST_PRICE    |    TAX_AMT    |    DISCOUNT    |    NET_AMT    |    PRD_DETAILS
--------------------------------------------------------------------------------------------------------------------------------
P01       |    DRILL MACHINE     |    1000.0        |    100.0      |    50.0        |    1050.0     |    P01:DRILL MACHINE
P02       |    WEIGHING MACHINE  |    1500.0        |    200.0      |    150.0       |    1550.0     |    P02:WEIGHING MACHINE
P03       |    HAMMER            |    100.0         |    10.0       |    5.0         |    105.0      |    P03:HAMMER

Computing Current Date value using Expression:
```````````````

NEW COLUMNS NAME         |    EXPRESSIONS
-----------------------------------------------------------------
CURRENT_DATE_VAL         |    CURRENT_DATE
CURRENT_DATETIME_VAL     |    CURRENT_TIMESTAMP

Output would contain below value

CURRENT_DATE_VAL         |    CURRENT_DATETIME_VAL
-----------------------------------------------------------------
2022-09-07               |    2022-09-07 10:05:12.432
