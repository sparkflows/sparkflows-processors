Join On Common Column
=========== 

This node joins the incoming dataframes using one common column between them.

Input
--------------
This node takes in 2 DataFrames as input and produces one DataFrame as output

Output
--------------
The output DataFrame is the result of joining the 2 incoming DataFrames on the selected join column

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeJoinUsingColumn

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - joinCol
        - Common Join Column
        - column on which to join
      * - joinType
        - JoinType
        - type of join
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


Join On Common Column Node Details
+++++++++++++++

This node joins the incoming dataframes using one common column between the two dataframes. 

Select the Common Join Column to be used in the Join.

Joining modes supported by this node is as follows:

*  inner : The joined table will have records that have matching values in both tables.
*  outer : The joined table contains either all the records from both the tables or fills in NULL values for missing matches on either side.
*  left_outer  : Even if there are no matches in the right table it returns all the rows from the left table.
*  right_outer : Even if there are no matches in the left table it returns all the rows from the right table.
*  leftsemi : This gives only those rows in the left table that have a matching row in the right table.
*  leftanti : This join returns rows in the left table that have no matching rows in the right table.


Examples
-------


Join On Common Column Example
+++++++++++++++

 Incoming Datasets
```````````````

1st Incoming Dataframe table1 has the following rows:

EMP_CD    |    EMP_NAME    |    DEPT_NO       
-------------------------------------------
E01       |    DAVID       |    10         
E02       |    JOHN        |    20      
E03       |    MARTIN      |    30  
E04       |    TONY        |    40  

2nd Incoming Dataframe table2 has the following rows:

DEPT_NO    |      DEPT_NAME   |    LOC       
-------------------------------------------
10         |      HR          |    IND  
20         |      SALES       |    AUS  
30         |      MARKETING   |    UK         
50         |      RESEARCH    |    NZ      

The common join column is DEPT_NO

 When the Joining condition is `inner` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |      DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |      HR         |    IND
E02       |    JOHN        |    20        |      SALES      |    AUS
E03       |    MARTIN      |    30        |      MARKETING  |    UK

 When the Joining condition `outer` we have
```````````````
 Final Output
```````````````

EMP_CD    |    EMP_NAME    |    DEPT_NO   |   DEPT_NAME  |    LOC           
--------------------------------------------------------------------------------------
E01       |    DAVID       |    10        |   HR         |    IND
E02       |    JOHN        |    20        |   SALES      |    AUS
E03       |    MARTIN      |    30        |   MARKETING  |    UK
E04       |    TONY        |    40        |              |    
          |                |              |   RESEARCH   |    NZ

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
E03       |    MARTIN      |    30        |   MARKETING  |    UK
          |                |    50        |   RESEARCH   |    NZ
