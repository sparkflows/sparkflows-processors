Union All
=========== 

This node creates a new DataFrame by doing a union of all the rows in the incoming Dataframes. It do not remove any duplicates.

Input
--------------
It accepts two or more DataFrames as input from the previous Nodes

Output
--------------
This node does union of all the rows without removing the duplicates

Type
--------- 

join

Class
--------- 

fire.nodes.etl.NodeUnionAll

Fields
--------- 



Details
-------


 Union All Node Details
+++++++++++++++

*  This node creates a new DataFrame by merging all the rows without removing the duplicates.
*  Data types of the column that you are trying to combine should match.
*  It accepts two or more DataFrames as input from the previous Nodes.
*  The resulting Dataframe is union of all the rows without removing the duplicates.


Examples
-------


 Union All Node Examples
+++++++++++++++

 Incoming Datasets
```````````````

1st Incoming Dataframe has following rows:

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E01       |    DAVID       |    HR         
E02       |    JOHN        |    SALES      
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  

2nd Incoming Dataframe has following rows:

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  
E05       |    MARK        |    HR         
E06       |    ROSS        |    SALES      

 Final Output
```````````````

Note that, UNION ALL keeps the duplicate records.

EMP_CD    |    EMP_NAME    |    DEPT       
-------------------------------------------
E01       |    DAVID       |    HR         
E02       |    JOHN        |    SALES      
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  
E03       |    MARTIN      |    MARKETING  
E04       |    TONY        |    MARKETING  
E05       |    MARK        |    HR         
E06       |    ROSS        |    SALES      
