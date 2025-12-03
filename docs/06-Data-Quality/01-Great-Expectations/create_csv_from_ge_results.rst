Create CSV from GE Results
===========



Type
--------- 

transform

Class
--------- 

fire.nodes.ge.NodeCreateCsvFromGeResults

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - csvPath
        - Path
        - Path to save consolidated Great Expectation results as a CSV
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite or Error if the path Exists
      * - header
        - Header
        - Should a Header Row be saved with each File?
      * - advanced
        - Advanced
        - 
      * - partitionColNames
        - Partition Column Names
        - Partition Column Names


Details
-------
Create CSV from GE Results Node
+++++++++++++++



Overview:
+++++++++++++++


This node writes the output of a GE pipeline to a CSV file. It offers flexibility in configuring the output file's path, save mode, and whether to include a header row.



Input:
+++++++++++++++


Path: The desired path for the output CSV file.

Save Mode: Determines how to handle existing files:

Append: Appends new data to the end of an existing file.

Overwrite: Overwrites the file with the new data.

ErrorIfExists: Throws an error if the file already exists.

Header: Specifies whether to include a header row with column names.



Output:
+++++++++++++++


The node writes the output DataFrame to the specified CSV file.


Examples
-------
Example:


Let's say you have a DataFrame containing customer data and want to save it as a CSV file.


Configure the Node:


Path: /path/to/output.csv

Save Mode: Append

Header: True

Node Execution:


The DataFrame will be written to the specified CSV file, appending new data if the file already exists. The output file will include a header row with column names.
