Concat Columns
=========== 

This node creates a new DataFrame by concatenating the specified columns of the input DataFrame

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
A new column is added to the incoming DataFrame by concatenating the specified columns. The new DataFrame is sent to the output of this Node.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeConcatColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Columns
        - Columns to be concatenated
      * - outputCol
        - Concatenated Column Name
        - Column name for the concatenated columns
      * - sep
        - Separator
        - Separator to be used when concatenating the columns


Details
-------


Concat Columns Node Details
+++++++++++++++

It adds a new column to the dataframe created by concatenating multiple columns and separated by the specified separator. 

Input
```````````````

*    COLUMNS :- Select columns that need to be concatenated. Multiple columns can be selected for concatenation.
*    CONCATENATED COLUMN NAME :- Enter name of the column to list the concatenated values in the outgoing Dataframe.
* 	  SEPARATOR :- Enter a Separator value to separate values from different columns in the output. It can be a multi-character value. Common Separator values used are as follows:

  a. #
  b. *
  c. -
  d. :
  e. [Blank Space]

Output
```````````````

*    New concatenated column would be added to the Outgoing Dataframe listing the concatenated values.


Examples
-------


Concat Columns Examples
+++++++++++++++

Incoming Dataframe
```````````````

In this example we have considered an Incoming Dataframe with following rows:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY
-------------------------------------------------------------------------------------
C01        |    MATT         |    50     |    12-02-2002         |    USD 200000.00
C02        |    LISA         |    45     |    15-11-2020         |    GBP 100000.00
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00
C04        |    MARCUS       |    35     |    01-01-2021         |    AUD 350000.00

Concat Columns Node Configuration and Output 
```````````````

Concat Columns Node is configured to concatenate two columns [CUST_CD] and [CUST_NAME] from the incoming Dataframe into a new column [CUST_IDENTIFIER] using separator [-].
Output Dataframe would be created as below:

CUST_CD    |    CUST_NAME    |    AGE    |    DATE_OF_JOINING    |    SALARY         |    CUST_IDENTIFIER
----------------------------------------------------------------------------------------------------------
C01        |    MATT         |    50     |    12-02-2002         |    USD 200000.00  |    C01-MATT
C02        |    LISA         |    45     |    15-11-2020         |    GBP 100000.00  |    C02-LISA
C03        |    ROBIN        |    30     |    10-10-2015         |    EUR 15000.00   |    C03-ROBIN
C04        |    MARCUS       |    35     |    01-01-2021         |    AUD 350000.00  |    C04-MARCUS
