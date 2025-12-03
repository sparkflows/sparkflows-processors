H2O ML Model Load
===========

Loads an H2O MOJO ML model

Type
--------- 

ml-modelload

Class
--------- 

fire.nodes.h2o.NodeH2OMojoLoad

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - selectChampionModel
        - Use Champion Model
        - Uses Champion Model For Prediction.
      * - path
        - Path To Load H2O model
        - Path for loading the H2O MOJO model


Details
-------
this node allows a previously trained and saved H2O model to be used again from the file system


Examples
-------
path-folder1/folder2/H2OModelFileName


the model saved in the path is fetched and can be sent to the prophet predict node to be used for prediction
