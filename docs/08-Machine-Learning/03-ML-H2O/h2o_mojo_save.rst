H2O ML Model Save
=========== 

Saves an H2O MOJO ML model at the specified path.

Input
--------------
It takes in a Model and DataFrame as input

Output
--------------
The incoming dataframe is passed to the output

Type
--------- 

ml-modelsave

Class
--------- 

fire.nodes.h2o.NodeH2OMojoSave

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
        - Path for saving the H2O MOJO
      * - fixedPath
        - Static path
        - Set this to true if you want model to be saved in a static path. It will overwrite the model in the directory specified.


Details
-------
this node saves the tained H2O model in the file system to be used in the future


Examples
-------
path-folder1/folder2/ModelFileName


the trained model will be saved to the given path,any folder not present will be created and exisiting model in the folder of the will be replaced
