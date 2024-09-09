Summary Statistics
=========== 

Summary statistics provide useful information about sample data. eg: measures of spread.

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeSummary

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
      * - colNames
        - Column Names
        - Column Names for Summary
      * - path
        - Path
        - Save Summary Statistics to Path


Details
-------


Summary Statistics Node Details
+++++++++++++++

The Summary Statistics node makes it easy to explore the contents of a DataFrame at a high level.

This node computes specified statistics which includes : - count - mean - stddev - variance - min - max - approximate percentiles specified as a percentage

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TITLE : A short description to summarize what the data depicts.
*  COLUMN NAMES : 

- Available : A list of numeric columns derived from the input dataframe schema.
- Selected : A list of numeric columns for whom the node will compute statistical values.

 


Examples
-------


Summary Statistics Node Example
+++++++++++++++

Consider the following DataFrame

ID  | CODE |
------------
1   | aa  |
2   | aa  |
9   | bb  |
5   | cc  |

 If we calculate the summary statistics for all columns in the DataFrame, we get 
```````````````

summary|      ID          |  CODE |
-----------------------------------
|  count|                4|      4|
|   mean|             4.25|   null|
|    min|                1|     aa|
|    25%|                1|   null|
|    50%|                2|   null|
|    75%|                5|   null|
|    max|                9|     cc|
| stddev|3.593976442141304|   null|
|variance|12.916667       |   null|
