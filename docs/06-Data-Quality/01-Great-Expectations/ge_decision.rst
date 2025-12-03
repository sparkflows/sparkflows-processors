GE Decision
=========== 

This Node takes in an expression. It evaluates the expression and based on the results sends the execution to the first or the second output Node

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
The incoming DataFrame is sent to the output. Only one of the output Nodes receives the DataFrame based on the results of the expression

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeGEDecision

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - expression
        - Expression
        - Expression to be evaluated. It can use variables computed in the previous Nodes
      * - status_file_path
        - Path
        - Path to generate _success and _failed directory.


Details
-------
GE Decision Node
---------------



Overview:
+++++++++++++++


The GE Decision node allows you to create complex decision logic within your data pipeline. It takes in a DataFrame and routes it based on specified conditions. You can use a variety of expressions and functions to define these conditions.



Input:
+++++++++++++++


Expression: A boolean expression that determines the output path.

Path: The path to which the data will be routed if the expression evaluates to true.


Output:
+++++++++++++++


The data is routed to the specified path based on the evaluation of the expression.


Examples
-------
Example
---------------


Let's say you want to split a DataFrame based on a column named is_high_value.


Configure the Node:


Expression: is_high_value == 1

Path: /high_value_data

Node Execution:


Rows where is_high_value is 1 will be routed to /high_value_data.

Rows where is_high_value is 0 or null will be routed to the default output path (if not specified).
