Join On Common Columns
=========== 

This node joins the incoming dataframes on 1 or more columns

Input
--------------
It takes in 2 or more DataFrames as input and produces one DataFrame as output by joining on the specified columns

Output
--------------
The output DataFrame produced as a result of joining the incoming DataFrames on the specified columns

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeJoinUsingColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - joinCols
        - Common Join Columns
        - Space separated list of columns on which to join
      * - joinType
        - Join Type
        - Type of Join
      * - whereClause
        - Where Clause
        - where condition after join function
      * - schema
        - Schema
      * - outputColNames
        - Output Column Names
        - Name of the Output Columns
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns


Details
-------


Join On Common Columns Node Details
+++++++++++++++

This node joins the incoming dataframes using one or more than one common column between the two dataframes. 

Join Types supported by this node are as follows

*  inner : The joined table will have records that have matching values in both tables.
*  outer : The joined table contains either all the records from both the tables or fills in NULL values for missing matches on either side.
*  left_outer  : Even if there are no matches in the right table it returns all the rows from the left table.
*  right_outer : Even if there are no matches in the left table it returns all the rows from the right table.
*  leftsemi : This gives only those rows in the left table that have a matching row in the right table.


The `WHERE CLAUSE` section is used to filter any records once the two or more tables have  been joined.


Examples
-------


Join On Common Columns Node Example
+++++++++++++++

 Incoming Dataframe
```````````````

1st Incoming dataframe table1 has the following rows:

EMP_CD    |    EMP_NAME    |    DEPT_NO    
-------------------------------------------
E01       |    DAVID       |    10         
E02       |    JOHN        |    20      
E03       |    MARTIN      |    30  
E04       |    TONY        |    40  

2nd Incoming dataframe table2 has the following rows:

DEPT_NO    |      DEPT_NAME   |    LOC     |   EMP_CD 
----------------------------------------------------
10         |      HR          |    IND     |   E01
20         |      SALES       |    AUS     |   E02
40         |      RESEARCH    |    NZ      |   E04
50         |      ADMIN       |    UK      |   E05

Selected common columns for both the dataframes are following 

*  From table1 is DEPT_NO and EMP_CD
*  From table2 is DEPT_NO and EMP_CD


 When the JOIN condition is `inner` with a WHERE clause of `DEPT_NO = 10` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |      DEPT_NAME  |    LOC   
-------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |      HR         |    IND

 When the JOIN condition is `inner` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |      DEPT_NAME  |    LOC   
-------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |      HR         |    IND
E02       |    JOHN        |    20        |      SALES      |    AUS
E04       |    TONY        |    40        |      RESEARCH   |    NZ

 When the Joining condition `outer` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |   HR         |    IND
E02       |    JOHN        |    20        |   SALES      |    AUS
E03       |    MARTIN      |    30        |              |    
E04       |    TONY        |    40        |   RESEARCH   |    NZ
E05       |                |    50        |   ADMIN      |    UK

 When the Joining condition is `left_outer` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |   HR         |    IND
E02       |    JOHN        |    20        |   SALES      |    AUS
E03       |    MARTIN      |    30        |   MARKETING  |    UK
E04       |    TONY        |    40        |              |    

 When the Joining condition `right_outer` we have
```````````````
 Final Output
```````````````
          
EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |   HR         |    IND
E02       |    JOHN        |    20        |   SALES      |    AUS
E04       |    MARTIN      |    30        |   RESEARCH   |    UK
E05       |                |    50        |   ADMIN      |    NZ
