Spark ML Model Save
=========== 

This node saves the ML model generated at the specified path.

Input
--------------
It takes in a Model and DataFrame as input.

Output
--------------
The incoming dataframe is passed to the output.

Type
--------- 

ml-modelsave

Class
--------- 

fire.nodes.ml.NodeModelSave

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
      * - fixedPath
        - Static path
        - Set this to true if you want model to be saved in a static path. It will overwrite the model in the directory specified.
      * - overwrite
        - Overwrite Output




