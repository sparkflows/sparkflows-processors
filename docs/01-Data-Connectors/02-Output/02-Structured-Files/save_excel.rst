Save Excel
===========

Saves the DataFrame into the specified location in XLS Format

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveExcel

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
        - Path where to save the XLS file
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - dataAddress
        - SheetName
        - SheetName and Range: 'My Sheet'!A1
      * - boxConnection
        - Box Connection
        - 
      * - accessToken
        - Access Token
        - 


Details
-------
Save Excel Node Details
+++++++++++++++


Saves the DataFrame into the specified location in XLS Format.



Parameters to be set:
+++++++++++++++


* OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
* PATH : Specify the path of the Excel file to be saved.
* SAVE MODE : Specify the save mode - Append, Overwrite, ErrorIfExists and Ignore.
* SHEETNAME : Specify the sheet name whose the data is to be saved.


Examples
-------
Save Excel Node Examples
+++++++++++++++



Example of Values
+++++++++++++++


* PATH : /tmp/sample.xlsx
* SAVE MODE : Overwrite
* SHEETNAME : Sheet1
