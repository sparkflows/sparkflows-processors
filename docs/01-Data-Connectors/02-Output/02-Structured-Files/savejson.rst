Save JSON
=========== 

Saves the DataFrame into the specified location in JSON Format

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveJSON

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
        - Path where to save the JSON files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names
      * - enableDownloadLink
        - Enable Download Link
        - Generate download links for the saved JSON files
      * - fileName
        - File Name To Download
        - Enter the FileName
      * - saveAsOneFile
        - Save as One File
        - Save the output as a single JSON file using coalesce


Details
-------
Save JSON Node Details
---------------


Saves the DataFrame into the specified location in JSON Format.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the JSON file to be saved.
* SAVE MODE : Specify the save mode - Append, Overwrite, ErrorIfExists and Ignore.


Examples
-------
Save JSON Node Examples
---------------



Example of Values
+++++++++++++++


* PATH : /tmp/sample.json
* SAVE MODE : Append
