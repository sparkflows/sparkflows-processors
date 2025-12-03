ExpectColumnToExist
===========



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeExpectColumnToExist

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - cols
        - Column Name
        - Comma separated column names.


Details
-------
Expect Column To Exist Node
+++++++++++++++



Overview:
+++++++++++++++


The Expect Column To Exist node checks if a specific column exists in a DataFrame. This is useful for ensuring data integrity and preventing errors in subsequent processing steps.



Input:
+++++++++++++++


Column Name: The name of the columns to check seperated by comma.



Output:
+++++++++++++++


The node will flag the pipeline as failed if the specified column does not exist.


Examples
-------
Example:


Let's assume we expect a column named age to be present in a DataFrame.


Configure the Node:


Column Name: age

Node Execution:


If the age column is not found, the node will fail the pipeline.
