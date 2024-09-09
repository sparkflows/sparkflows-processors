Execute In Loop
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDistinctValuesLoop

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - loopCols
        - Loop Columns
        - 


Details
-------


 Execute In Loop Node Details
+++++++++++++++

The Execute In Loop Node loops through an iterable object and perform the same action for each entry.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  LOOP COLUMNS : The distinct column values for which the loop with iterate through.

- Available : Columns available as part of the input Dataframe schema. 
- Selected : The columns against which the loop will iterate through


Examples
-------


Execute In Loop Node Example
+++++++++++++++

Consider the below dataframe which contains sales figures for a product as shown below:

PRD_CD    |      DATE        |    SALESAMT   | 	
---------------------------------------------
A001     |      2022-02-01   |    15000      |
A001     |      2022-02-02   |    22000      |
A001     |      2022-02-03   |    8000       |
A002     |      2022-02-01   |    11000      |
A003     |      2022-02-03   |    32000      |

Assuming we use the 'DATE' column in our 'Selected' loop columns, on execution of this node we will have the loop  
group the records based on the `DATE` column values and iterate through the records in that sequence.
