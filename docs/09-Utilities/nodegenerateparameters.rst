Generate Dynamic Parameters
===========

This node create dynamic parameters for each column and value. ParameterName is ColumnName and Parameter Value in value from first row.

Type
--------- 

shellcommand

Class
--------- 

fire.nodes.util.NodeGenerateDynamicParameter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Column Name to generate dynamic parameters


Details
-------
Generate Dynamic Parameters
+++++++++++++++


The Generate Dynamic Parameters Node generate the column name and value as Dynamic Parmaeters(value) aviable in next node.


User can access the value in next node like ${COLUMN_NAME}


