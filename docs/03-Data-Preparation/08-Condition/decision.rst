Decision
=========== 

It computes expressions to determine if the condition is met or not. Accordingly proceeds to the next step or stops here.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDecision

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
        - Description
      * - inputCols
        - Columns
        - Columns
      * - functions
        - Function
        - Function to apply
      * - symbols
        - Symbol
        - Symbol to apply
      * - values
        - Values
        - Values


Details
-------


Decision Node Details
+++++++++++++++

It evaluates an expression to determine if the condition is met or not. Based on the evaluation output it proceeds to the next step or stops the execution of the process.

If expression evaluates to true then incoming Dataframe is sent to the output node and it is executed otherwise execution terminates in this node.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  DESCRIPTION : Enter a short description on how the node is being used.
*  VARIABLES : We can specify one or more evaluation criteria on the available columns

- Columns : Column/Field name available for specifying the evaluation criteria. 
- Function : COUNT_RECORDS function which counts the number of records for the specified column
- Symbol : Evaluate the expression based on the criteria of greater than, less than or Is equal to
- Values :  The number of records against which the condition is to be evaluated


Examples
-------


Decision Node Example
+++++++++++++++

Consider the Decision node to be configured for a dataframe which contains the column of `PRD_CD` as shown below:

COLUMNS    |      FUNCTION        |    SYMBOL    |    VALUES 	
---------------------------------------------------------------
PRD_CD     |      COUNT_RECORDS   |    <         |    10

If count of entries in [PRD_CD] is less then 10, Only then would the execution process continue. If it evaluated to false then the execution stops at this node.
