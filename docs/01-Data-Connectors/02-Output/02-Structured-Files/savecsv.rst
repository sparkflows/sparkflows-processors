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
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names


Details
-------


This node saves incoming Dataframe into the specified location in CSV format.


