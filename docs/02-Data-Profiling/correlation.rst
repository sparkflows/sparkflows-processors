Correlation
=========== 

calculates the correlation between two series of data.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The input DataFrame is passed along to the next Processors

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeCorrelation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - title
        - Title
      * - inputCols
        - Input Column for Correlation
        - Column Names to check correlation 


Details
-------


Correlation Node Details
+++++++++++++++

Correlation is to measure if two variables or two feature columns tend to move in together in same or opposite direction. The idea is to detect if one variable or feature column can be predicted by another variable or feature column.

The Correlation node uses the method of Pearson's correlation for checking correlation between two continuous variables (or feature columns)

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TITLE : A short description to summarizes what the data depicts.
*  INPUT COLUMN FOR CORRELATION : 

- Available : A list of numeric columns derived from the input dataframe schema.
- Selected : A list of numeric columns among which the correlation is to be predicted.
 


Examples
-------


Correlation Node Example
+++++++++++++++

For a given dataframe having the below schema:
Course  | Amount | Discount| 
(String)| Double | Double  |
----------------------------

We can select the <b>Amount</b> and <b>Discount</b> fields for which we need to find the correlation.

This will yield three separate output sections:
- A Correlation Table
- A Correlation Matrix &
- A sample data values of the input dataframe
