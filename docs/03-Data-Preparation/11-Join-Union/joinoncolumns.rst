Join On Columns
=========== 

Joins the incoming Dataframes on the given columns

Type
--------- 

join2inputs

Class
--------- 

fire.nodes.etl.JoinOnColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - joinType
        - Join Type
        - Type of Join
      * - leftTableJoinColumn
        - LeftTableJoinColumn
        - 
      * - rightTableJoinColumn
        - RightTableJoinColumn
        - 


Details
-------


Join On Columns Node Details
+++++++++++++++


*  This node joins the incoming dataframes based on a specified column between the two dataframes.
*  The new Dataframe will contain all the columns from both Dataframe.


Joining modes supported by this node are as follows:

*  inner : The joined table will have records that have matching values in both tables.
*  outer : The joined table contains either all the records from both the tables or fills in NULL values for missing matches on either side.
*  left_outer  : Even if there are no matches in the right table it returns all the rows from the left table.
*  right_outer : Even if there are no matches in the left table it returns all the rows from the right table.
*  leftsemi : This gives only those rows in the left table that have a matching row in the right table.


Examples
-------


Join On Columns Example
+++++++++++++++

 Incoming Dataframes
```````````````

1st Incoming Dataframe table1 has the following rows:

EMP_CD    |    EMP_NAME    |    DEPT_NO       
-------------------------------------------
E01       |    DAVID       |    10         
E02       |    JOHN        |    20      
E03       |    MARTIN      |    30  
E04       |    TONY        |    40  

2nd Incoming Dataframe table2 has the following rows:

DEPT_ID    |      DEPT_NAME   |    LOC       
-------------------------------------------
10         |      HR          |    IND  
20         |      SALES       |    AUS  
30         |      MARKETING   |    UK         
50         |      RESEARCH    |    NZ      

 Selected columns for joining are following 
```````````````

*  From table1 is DEPT_NO
*  From table2 is DEPT_ID


 When the Joining condition is `inner` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_ID    |      DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |     10       |      HR         |    IND
E02       |    JOHN        |    20        |     20       |      SALES      |    AUS
E03       |    MARTIN      |    30        |     30       |      MARKETING  |    UK

 When the Joining condition `outer` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_ID    |      DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |     10       |      HR         |    IND
E02       |    JOHN        |    20        |     20       |      SALES      |    AUS
E03       |    MARTIN      |    30        |     30       |      MARKETING  |    UK
E04       |    TONY        |    40        |              |                 |    
          |                |              |     50       |      RESEARCH   |    NZ

 When the Joining condition is `left_outer` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_ID    |      DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |     10       |      HR         |    IND
E02       |    JOHN        |    20        |     20       |      SALES      |    AUS
E03       |    MARTIN      |    30        |     30       |      MARKETING  |    UK
E04       |    TONY        |    40        |              |                 |    

 When the Joining condition `right_outer` we have
```````````````
 Final Output
```````````````
          
EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_ID    |      DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |     10       |      HR         |    IND
E02       |    JOHN        |    20        |     20       |      SALES      |    AUS
E03       |    MARTIN      |    30        |     30       |      MARKETING  |    UK
          |                |              |     50       |      RESEARCH   |    NZ
