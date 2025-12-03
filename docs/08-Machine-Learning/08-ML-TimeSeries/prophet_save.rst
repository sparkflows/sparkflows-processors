Prophet Model Save
===========

This node saves the Prophet model generated at the specified path in pickle file.

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

fire.nodes.ts.NodeProphetSave

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
        - 


Details
-------
this node saves the tained prohet model in the file system to be used in the future


Examples
-------
path-folder1/folder2/ModelFileName


the trained model will be saved to the given path,any folder not present will be created and exisiting model in the folder of the will be replaced
