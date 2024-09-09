Union Distinct
=========== 

This node creates a new DataFrame by performing a UNION of all the rows in the incoming Dataframe. It then performs DISTINCT on the result set, eliminating any duplicate rows

Input
--------------
It takes in multiple DataFrames as input

Output
--------------
This node does union of all the rows from the incoming DataFrames to generate the output DataFrame. It also removes the duplicate rows from the resulting Dataframe.

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeUnionDistinct

Fields
--------- 



Details
-------


 Union Distinct Node Details
+++++++++++++++


*  This node creates a new DataFrame by performing a DISTINCT on the result set, eliminating any duplicate rows.
*  It can take two or more DataFrames as input.
*  Data types of the column that you are trying to combine should match.
*  This node combines the results of the incoming DataFrames to generate a single result set that contains the rows without any duplicates.


Examples
-------


 Union Distinct Example
+++++++++++++++

Incoming Dataframe
```````````````

1st Incoming Dataframe has the following rows:

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E01       |    DAVID       |    HR         
E02       |    JOHN        |    SALES      
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  

2nd Incoming Dataframe has the following rows:

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  
E05       |    MARK        |    HR         
E06       |    ROSS        |    SALES

Final Output
```````````````

After execution of UnionDistinct node following outgoing Dataframe would be created after combining all rows from all input Dataframes and removing duplicate rows.
Outgoing Dataframe contains only distinct rows:

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E01       |    DAVID       |    HR         
E02       |    JOHN        |    SALES      
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  
E05       |    MARK        |    HR         
E06       |    ROSS        |    SALES      
