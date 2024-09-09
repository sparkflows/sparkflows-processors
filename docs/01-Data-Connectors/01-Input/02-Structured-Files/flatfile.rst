ReadFlatFile
=========== 

Creates a dataset with output schema from schema field with values extracted from fixedlength.

Input
--------------
It does not read data from any external source

Output
--------------
It creates a DataFrame with columns from schema field.

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeReadFlatFile

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - path
        - Path
        - Path of the file/directory
      * - schema
        - Schema Details
        - Schema details: ColumnName, LengthOfTheField




