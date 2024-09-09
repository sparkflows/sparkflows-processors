Save Delta
=========== 

Saves the DataFrame into the specified location in Delta Format. When running on Hadoop, it is saved onto HDFS.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveDelta

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
        - Path to save the delta files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names




