Join On Common Columns
=========== 

This node joins the incoming dataframes on 1 or more columns

Input
--------------
It takes in 2 DataFrames as input and produces one DataFrame as output by joining on the specified columns

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




