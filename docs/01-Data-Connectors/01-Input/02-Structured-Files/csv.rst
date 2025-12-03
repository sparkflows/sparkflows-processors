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
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names for the CSV
        - New Columns from CSV
      * - outputColTypes
        - Column Types for the CSV
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the CSV
        - Format of the Output Columns
      * - properties
        - Properties
        - 
      * - extraOptionsKeys
        - Properties Name
        - Extra options/properites available while executing in Read CSV.
      * - extraOptionsValues
        - Properties Value
        - Config Values for the Corresponding properites name


Details
-------
Read CSV Details
---------------


This node reads CSV files and creates a DataFrame from them. It can read either a single file or a directory containing multiple files. The user can configure the below fields to parse the file.


The user can choose the **Output storage level** from the drop down. The options in the dropdown can be one of the following:


* **MEMORY_ONLY**          Store RDD as deserialized Java objects in the JVM. If the RDD does not fit in memory, some partitions will not be cached and will be recomputed on the fly each time they are needed. This is the default level.
* **MEMORY_AND_DISK**       Store RDD as deserialized Java objects in the JVM. If the RDD does not fit in memory, store the partitions that do not fit on disk, and read them from there when they are needed.
* **MEMORY_ONLY_SER**        Store RDD as serialized Java objects (one byte array per partition). This is generally more space-efficient than deserialized objects, especially when using a fast serializer, but more CPU-intensive to read.
* **MEMORY_AND_DISK_SER**    Similar to MEMORY_ONLY_SER, but spill partitions that do not fit in memory to disk instead of recomputing them on the fly each time they're needed.
* **DISK_ONLY**              Store the RDD partitions only on disk.
* **MEMORY_ONLY_2, MEMORY_AND_DISK_2 others ** . Same as the levels above, but replicate each partition on two cluster nodes.
* **OFF_HEAP**               Similar to MEMORY_ONLY_SER, but store the data in off-heap memory. This requires off-heap memory to be enabled.


The user needs to provide a data file **Path** to read the data from. This is a required field.


The user can choose the **Separator** used in the data file to parse it. The default separator is **( , )** comma.


In the **Header** field, one can choose:


* **true** if the data file has a header.
* **false** Otherwise.


In the **Drop special character in column name** field, one can choose:


* **true** If you want to remove the special characters from column names.
* **false** Otherwise.


In the **Mode** field, one can choose from the below options in the dropdown:


* **PERMISSIVE** When the parser meets a corrupt field in a record, it sets the value of the field to NULL and continues to the next record.
* **DROPMALFORMED** ignores the whole corrupted record.
* **FAILFAST** throws an exception when it meets corrupted records.


In the **Enforce Schema** field, one can choose:


* **true** The specified or inferred schema will be forcibly applied to datasource files, and headers in CSV files will be ignored.
* **false** The schema will be validated against all headers in CSV files when the header option is set to **false**.


In the **Whether to add input file as a column in DataFrame** field, one can choose:


* **true** There will be a new column added to the DataFrame at the end, which can be seen in the schema columns. One can enter the name of this column.
* **false** This functionality is disabled, and the DataFrame consists of only the columns read from the data file.


In the **ENCODING** field, one can specify the encoding type to be used for reading the files. By default, it is set as **UTF-8**.


The **QUOTE** field sets a single character used for escaping quoted values where the separator can be part of the value. The default value for this is **( " )**, a double quote.


The **ESCAPE** field sets a single character used for escaping quotes inside an already quoted value. The default value for this is **( \ )**, a backslash.    


After the above options are set, one can click on **InferSchema** to see the final columns.

Users can still add or delete columns using **+** button next to the InferSchema and **-** button next to the column names.


Examples
-------
Read CSV Node Example
---------------


Given a CSV file with the following data:


SupplierID,SupplierName,Region,YearsInBusiness,LeadTime,PriceIndex,OrderFulfillmentTime,OverallCost,OrderCancellations,CustomerRating

S1,Supplier A,Region 1,10,5,1.2,3,100,2,4

S2,Supplier B,Region 2,15,7,1.1,4,120,1,5

If you configure the Read CSV node as follows:


Path: /path/to/your/file.csv

Separator: ,

Header: true

The output would be a DataFrame with the following schema:


Column Name    Data Type

SupplierID    String

SupplierName    String

Region    String

YearsInBusiness    Integer

LeadTime    Integer

PriceIndex    Double

OrderFulfillmentTime    Integer

OverallCost    Integer

OrderCancellations    Integer

CustomerRating    Integer
