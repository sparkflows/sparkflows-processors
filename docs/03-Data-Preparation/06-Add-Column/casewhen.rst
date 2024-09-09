Case When
=========== 

This node creates a new Dataframe with a new column appended to it containing value based on the condition met

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeCaseWhen

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCol
        - Output Column Name
        - output column name
      * - whenConditions
        - When
        - When Condition
      * - values
        - Then
        - Value when this condition is true
      * - finallyElse
        - Else
        - else


Details
-------


Case When Node Details
+++++++++++++++

This node creates a new Dataframe with new output column added to the incoming dataframe. Value of the new column is set based on the Condition met and corresponding value fetched.

It evaluates a set of expressions and outputs value of the expression that evaluates to true. If none of the expressions evaluates to true then it outputs value assigned in the 'else' section.

When conditions can be entered as followings:
###############

Using Comparison Operators
```````````````

* 	Comparing a value against a String column		->		Example:	PRD_CATEGORY = 'MACHINE'
* 	Checking for not equal to condition against a String column		->		Example:	PRD_CATEGORY != 'MACHINE'
* 	Comparing a value against a Numeric column		->		Example:	AGE >= 35
* 	Using a Mathematical operator					->		Example:	(AGE * 10) < 90
*  Checking for multiple values using IN and NOT IN  ->  Example:    DEPT IN ('HR', 'SALES')


Using Logical Operators To Combine Multiple Expressions
```````````````

* 	Checking for two conditions in single expression	->		Example:	DEPT = 'HR' AND AGE >= 25
* 	Checking for two conditions in single expression		->		Example:	AGE >= 35 OR AGE <45


Checking For Null Value
```````````````

* 	Checking whether a column value is Null			->		Example:	DEPT IS NULL


Checking For Blank Value
```````````````

* 	Checking whether value in a column is empty		->		Example:	TRIM(DATE_OF_JOINING) = ''


Checking Against Boolean Value
```````````````

* 	Checking whether a Boolean column is True or False		->		Example:	IS_DATEGREATER = TRUE


Checking Against Date-Time Value
```````````````

* 	Comparing a Date column against a Date value	->		Example:	CURR_DATE > TO_DATE('2021-12-12','yyyy-MM-dd')
* 	Comparing a Date-Time column against a Date-Time value	->		Example:	CURR_TIME > TO_TIMESTAMP('2021-12-12 12:12:12','yyyy-MM-dd HH:mm:ss')



Values can entered as followings:
###############

Assigning value from a column
```````````````

*  	Assigning value from a column[DEPT] to output (Value)		->		Example:	DEPT
*  	Applying a operator before assigning value from a column		->		Example:	SALARY * 10


Assigning a String or Number constant
```````````````

* 	Assigning a String constant		->		Example:	'DEPT IS HR'
* 	Assigning a Number constant		->		Example:	1000


Assigning Current Date and Current Timestamp
```````````````

* 	Assigning Current Date		->		Example:	CURRENT_DATE
* 	Assigning Current Date-Time		->		Example:	CURRENT_TIMESTAMP


Examples
-------


Case When Node Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered a Incoming Dataframe with following rows:

EMP_CD    |    EMP_NAME    |    DEPT       |    AGE    |    DATE_OF_JOINING   |    PERFORMANCE     |    SALARY
------------------------------------------------------------------------------------------------------------------
E01       |    DAVID       |    HR         |    25     |    2021-01-01        |    GOOD            |    12000
E02       |    JOHN        |    SALES      |    35     |    2019-05-04        |    VERY GOOD       |    11000
E03       |    MARTIN      |    MARKETING  |    40     |    2018-06-07        |    AVERAGE         |    34000
E04       |    TONY        |    MARKETING  |    45     |    2017-02-01        |    VERY VERY GOOD  |    12500
E05       |    MARK        |    HR         |    25     |    2020-12-21        |    BAD             |    78999

CaseWhen Node Configuration
```````````````

CaseWhen node is configured as below to compute values for the output column:

WHEN CONDITION                        |        VALUE
------------------------------------------------------------------
SALARY < 12500                        |        'FIRST_GRADE'
SALARY>= 12500 AND SALARY < 30000     |        'SECOND_GRADE'
SALARY >- 30000 AND SALARY < 70000    |        'THIRD_GRADE'
ELSE                                  |        'FOURTH_GRADE'

[ELSE] is the default condition processed if no other condition is met

Node Output
```````````````

Output Dataframe would be created as below where value of [SALARY] is compared against [WHEN CONDITION] and [VALUE] is fetched for the output column [SALARY_GRADE]:

EMP_CD    |    EMP_NAME    |    DEPT       |    AGE    |    DATE_OF_JOINING   |    PERFORMANCE     |    SALARY    |    SALARY_GRADE
---------------------------------------------------------------------------------------------------------------------------------------
E01       |    DAVID       |    HR         |    25     |    2021-01-01        |    GOOD            |    12000     |    FIRST_GRADE
E02       |    JOHN        |    SALES      |    35     |    2019-05-04        |    VERY GOOD       |    11000     |    FIRST_GRADE
E03       |    MARTIN      |    MARKETING  |    40     |    2018-06-07        |    AVERAGE         |    34000     |    THIRD_GRADE
E04       |    TONY        |    MARKETING  |    45     |    2017-02-01        |    VERY VERY GOOD  |    12500     |    SECOND_GRADE
E05       |    MARK        |    HR         |    25     |    2020-12-21        |    BAD             |    78999     |    FOURTH_GRADE

 Values can also be assigned based on the value of another column
```````````````

if CaseWhen node is configured as below to compute values for the output column:

WHEN CONDITION                        |        VALUE
------------------------------------------------------------------
SALARY IS NULL                        |        AGE
ELSE                                  |        SALARY
