Save CSV
=========== 

Saves the DataFrame into the specified location in CSV Format

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveCSV

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
        - Path where to save the CSV files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - header
        - Header
        - Should a Header Row be saved with each File?
      * - encoding
        - Encoding
        - Decodes the CSV files by the given encoding type
      * - quote
        - Quote
        - Sets a single character used for escaping quoted values where the separator can be part of the value
      * - escape
        - Escape
        - Sets a single character used for escaping quotes inside an already quoted value.
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names
      * - enableDownloadLink
        - Enable Download Link
        - Generate download links for the saved CSV files
      * - fileName
        - File Name To Download
        - Enter the FileName
      * - saveAsOneFile
        - Save as One File
        - Save the output as a single CSV file using coalesce


Details
===============
This node saves incoming Dataframe into the specified location in CSV format.


Examples
===============
path-folder1/folder2/filename


the file will be saved under the file name at the path provided

if folder is not present it will be created and save the file

if the file already exists selection in save mode determines what happens to the file,append-adds the file data to it overwrite-replaces the file altogether
