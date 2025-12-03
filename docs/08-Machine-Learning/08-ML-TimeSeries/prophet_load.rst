Prophet Model Load
===========

This node load the Prophet model stored in the pickel file.

Type
--------- 

ml-modelload

Class
--------- 

fire.nodes.ts.NodeProphetLoad

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
this node allows a previously trained and saved prophet model to be used again from the file system


Examples
-------
path-folder1/folder2/ModelFileName


the model saved in the path is fetched and can be sent to the prophet predict node to be used for prediction
