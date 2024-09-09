Read CSV
=========== 

It reads in CSV files and creates a DataFrame from it.

Input
--------------
It reads in CSV text files

Output
--------------
It creates a DataFrame from the data read and sends it to its output

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetCSV

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
        - Path of the file/directory
      * - separator
        - Separator
        - CSV Separator
      * - header
        - Header
        - Whether the file has a header row
      * - dropSpecialCharacterInColumnName
        - Drop Special Character In ColumnName
        - Whether to drop the Special Characters and Spaces in Column Name.
      * - mode
        - Mode
        - Mode for dealing with corrupt records during parsing.
      * - enforceSchema
        - Enforce Schema
        - If it is set to true, the specified or inferred schema will be forcibly applied to datasource files, and headers in CSV files will be ignored. If the option is set to false, the schema will be validated against all headers in CSV files in the case when the header option is set to true.
      * - addInputFileName
        - Whether to Add Input File Name as Column in the Dataframe
        - Add the new field:input_file_name
      * - encoding
        - Encoding
        - Decodes the CSV files by the given encoding type
      * - quote
        - Quote
        - Sets a single character used for escaping quoted values where the separator can be part of the value
      * - escape
        - Escape
        - Sets a single character used for escaping quotes inside an already quoted value.
      * - outputColNames
        - Column Names for the CSV
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types for the CSV
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the CSV
        - Format of the Output Columns


Details
-------


Read CSV Details
+++++++++++++++

This node reads CSV files and creates a DataFrame from them. It can read either a single file or a directory containing multiple files. The user can configure the below fields to parse the file.

The user can choose the <b>Output storage level</b> from the drop down. The options in the dropdown can be one of the following:

*  <b>MEMORY_ONLY</b>          Store RDD as deserialized Java objects in the JVM. If the RDD does not fit in memory, some partitions will not be cached and will be recomputed on the fly each time they are needed. This is the default level.
*  <b>MEMORY_AND_DISK</b>       Store RDD as deserialized Java objects in the JVM. If the RDD does not fit in memory, store the partitions that do not fit on disk, and read them from there when they are needed.
*  <b>MEMORY_ONLY_SER</b>        Store RDD as serialized Java objects (one byte array per partition). This is generally more space-efficient than deserialized objects, especially when using a fast serializer, but more CPU-intensive to read.
*  <b>MEMORY_AND_DISK_SER</b>    Similar to MEMORY_ONLY_SER, but spill partitions that do not fit in memory to disk instead of recomputing them on the fly each time they're needed.
*  <b>DISK_ONLY</b>              Store the RDD partitions only on disk.
*  <b>MEMORY_ONLY_2, MEMORY_AND_DISK_2 others </b> . Same as the levels above, but replicate each partition on two cluster nodes.
*  <b>OFF_HEAP</b>               Similar to MEMORY_ONLY_SER, but store the data in off-heap memory. This requires off-heap memory to be enabled.


The user needs to provide a data file <b>Path</b> to read the data from. This is a required field.

The user can choose the <b>Separator</b> used in the data file to parse it. The default separator is <b>( , )</b> comma.

In the <b>Header</b> field, one can choose:

*  <b>true</b> if the data file has a header.
*  <b>false</b> Otherwise.


In the <b>Drop special character in column name</b> field, one can choose:

*  <b>true</b> If you want to remove the special characters from column names.
*  <b>false</b> Otherwise.


In the <b>Mode</b> field, one can choose from the below options in the dropdown:

*  <b>PERMISSIVE</b> When the parser meets a corrupt field in a record, it sets the value of the field to NULL and continues to the next record.
*  <b>DROPMALFORMED</b> ignores the whole corrupted record.
*  <b>FAILFAST</b> throws an exception when it meets corrupted records.


In the <b>Enforce Schema</b> field, one can choose:

*  <b>true</b> The specified or inferred schema will be forcibly applied to datasource files, and headers in CSV files will be ignored.
*  <b>false</b> The schema will be validated against all headers in CSV files when the header option is set to <b>false</b>.


In the <b>Whether to add input file as a column in DataFrame</b> field, one can choose:

*  <b>true</b> There will be a new column added to the DataFrame at the end, which can be seen in the schema columns. One can enter the name of this column.
*  <b>false</b> This functionality is disabled, and the DataFrame consists of only the columns read from the data file.


In the <b>ENCODING</b> field, one can specify the encoding type to be used for reading the files. By default, it is set as <b>UTF-8</b>.

The <b>QUOTE</b> field sets a single character used for escaping quoted values where the separator can be part of the value. The default value for this is <b>( " )</b>, a double quote.

The <b>ESCAPE</b> field sets a single character used for escaping quotes inside an already quoted value. The default value for this is <b>( \ )</b>, a backslash.	

After the above options are set, one can click on <b>Refresh Schema</b> to see the final columns.
Users can still add or delete columns using <b>+</b> button next to the refresh schema and <b>-</b> button next to the column names.


