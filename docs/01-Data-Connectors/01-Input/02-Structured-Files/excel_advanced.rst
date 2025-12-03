Read Excel Advanced
=========== 

Advanced Excel Reader Node – Load one or more sheets, named ranges, or specific cell ranges from .xlsx/.xls files with full control over headers, data types, and metadata columns. Perfect for business reports, financial models, and mixed-format Excel sources.

Input
--------------
Reads data from Excel files (.xlsx, .xls) with support for sheets, ranges, and custom schemas.

Output
--------------
Returns a DataFrame containing the Excel data with proper column names and types.

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetExcelAdvanced

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
        - Full path to the Excel file or folder. Supports local paths, HDFS, S3, GCS, Azure, etc. Example: /data/sales.xlsx or s3a://my-bucket/reports/
      * - boxConnection
        - Box Connection
        - 
      * - accessToken
        - Access Token
        - 
      * - recdirectorysearch
        - Read subdirectory recursively
        - If the path is a directory, recursively scan all subfolders for Excel files. Useful when processing many files at once.
      * - readAllSheets
        - Read All Sheets
        - Automatically read every sheet in the workbook and union them into one DataFrame. Great for files where each sheet has the same structure (e.g., monthly tabs).
      * - selectedSheets
        - Select Sheets
        - Comma-separated list of sheet names or indices to import (e.g., Sheet1,Summary,2023 Data or 0,2,5). Leave empty if reading only one sheet or using Read All Sheets.
      * - dataAddressMode
        - Data Source Mode
        - Choose how to specify which part of the sheet to read: FullSheet Read the entire sheet starting from the defined start line (default & fastest) CellRange – Import only a specific cell range (e.g., A5:Z1000). Ideal for very large sheets or when you only need a table inside the sheet NamedRange – Use a predefined named range from Excel (e.g., SalesData, ReportTable). Most reliable when the table position changes
      * - startLine
        - Start Data Import on Line
        - Row number (1 = first row) where actual data begins. Useful when Excel files have titles, logos, or blank rows at the top.
      * - range
        - Range
        - Excel-style cell range in A1 notation (e.g., A1:F1000, B5:Z500). Limits reading to only these cells – perfect for very large sheets.
      * - header_option
        - Header Handling Mode
        - How to treat headers: • NO_HEADER – columns become _c0, _c1, etc. • FIRST_ROW – first row at Start Line becomes column names • PREVIOUS_ROW – row before Start Line is header • CUSTOM_ROW – specify exact header row(s)
      * - customHeaderRow
        - Custom Header Row
        - Row number or range (e.g., 5 or 5:7 for multi-row headers) to use as header. Only active when Header Handling Mode = CUSTOM_ROW.
      * - importSheetNamesOnly
        - Import Only Sheet Names
        - Instead of data, output a simple list of all sheet names in the workbook. Ideal for discovery or dynamic sheet selection workflows.
      * - dropSpecialCharacterInColumnName
        - Drop Special Character In Column Name
        - Automatically clean column names by replacing spaces, #, *, /, etc. with underscores and removing invalid characters. Recommended for downstream compatibility.
      * - schema
        - InferSchema
        - 
      * - outputFileName
        - Output File Name as Field
        - Add source file info as a new column: • no – nothing added • filename – just the file name (e.g., report.xlsx) • fullpath – complete path (useful for traceability)
      * - sheetNameDisplay
        - Output Sheet Name as Field
        - Adds a new column sheet_name containing the source sheet for each row. Essential when reading multiple sheets together.
      * - enforceSchema
        - Enforce Schema
        - Forcefully apply the defined schema (column names & types). Ignores Excel headers completely and casts all data – use when Excel headers are unreliable or missing.
      * - outputColNames
        - Column Names for the Excel
        - Explicitly define output column names. Overrides any header from Excel. Leave empty to use Excel headers (or auto-generated names).
      * - outputColTypes
        - Column Types for the Excel
        - Force column data types (String, Integer, Long, Double, Boolean, Date, Timestamp). Critical for correct calculations and joins.
      * - outputColFormats
        - Column Formats for the Excel
        - Date/timestamp format patterns (e.g., yyyy-MM-dd, dd/MM/yyyy HH:mm:ss). Only needed when Excel stores dates as text or custom formats.
      * - interactiveRunConfiguration
        - Interactive Run Configuration
        - 
      * - limitInputRecords
        - Limit Input Records
        - Maximum rows to preview in interactive/design mode (default 20). Does not affect batch execution.
      * - dataSampling
        - Data Sampling
        - How to sample data in interactive mode: • Random – picks random rows • Selective – use a filter expression to choose exactly which rows to preview
      * - selectiveSamplingExpression
        - Selective Filter Expression
        - SQL-like filter to pull specific rows in interactive mode (e.g., "Region = 'North' AND Year = 2024"). Only active when Data Sampling = Selective.


Details
===============
Read Excel Advanced Node – Complete Guide
---------------

The Read Excel Advanced node is the most powerful and flexible way to import Excel files into your pipeline. It handles real-world business Excel files with multiple sheets, merged cells, titles, footers, and inconsistent formatting – all while giving you full control over schema, metadata, and performance.



When to Use This Node
+++++++++++++++


* Business reports with headers starting on row 5–10
* Workbooks where each month/year is a separate sheet with identical layout
* Need to read only a specific table from a huge sheet
* Requirement to trace source file and sheet name for audit/compliance
* Excel files with messy column names (spaces, special chars)


Key Features
+++++++++++++++

* Read single sheet, multiple sheets, all sheets
* Precise cell range selection (A1 notation)
* Multi-row or custom-row headers
* Automatic or forced schema with type casting
* Adds filename and sheet_name columns for traceability
* Recursively processes folders of Excel files
* Cleans column names automatically
* High performance even on large workbooks


Core Parameters Explained
+++++++++++++++



Path
+++++++++++++++


Full location of the Excel file or folder (supports HDFS, S3, GCS, ADLS, local, etc.).



Read All Sheets + Select Sheets
+++++++++++++++

Combine both for advanced use: read only specific sheets from many files, or read all sheets and union them.



Start Data Import on Line
+++++++++++++++

Skip logos, titles, or blank rows at the top – common in finance and reporting files.



Range
+++++++++++++++

Read only the exact table you need – ignore charts, comments, and extra data.



Header Handling Mode
+++++++++++++++

Flexible options for any header layout Excel users create.



Enforce Schema
+++++++++++++++

Critical when Excel headers change or are missing – guarantees stable column names and types downstream.



Output File Name / Sheet Name as Field
+++++++++++++++

Essential for audit trails and debugging when processing hundreds of files.



Schema Tab (InferSchema)
+++++++++++++++

Define exact column names, data types, and date formats. When Enforce Schema = true, these override everything in the Excel file.


Examples
===============
Read Excel Advanced – Real-World Examples
---------------



Example 1 – Monthly Sales Files (One Sheet per Month)
+++++++++++++++



Scenario
+++++++++++++++

Folder contains 12 files: Sales_Jan.xlsx, Sales_Feb.xlsx, ..., each with a sheet "Data" starting at row 6 (rows 1–5 are titles).



Configuration
+++++++++++++++


* Path: /data/sales_monthly/
* Read subdirectory recursively: false
* Selected Sheets: Data
* Start Data Import on Line: 6
* Header Handling Mode: FIRST_ROW
* Output File Name as Field: filename
* Drop Special Character In Column Name: true


Result
+++++++++++++++


One unified DataFrame with a filename column showing which month each row came from.



Example 2 – All Sheets Have Same Structure (Yearly Workbook)
+++++++++++++++



Scenario
+++++++++++++++

File "2024_Sales.xlsx" has 12 sheets: Jan, Feb, ..., Dec – all with identical columns.



Configuration
+++++++++++++++


* Path: /data/2024_Sales.xlsx
* Read All Sheets: true
* Start Data Import on Line: 1
* Header Handling Mode: FIRST_ROW
* Output Sheet Name as Field: true
* Drop Special Character In Column Name: true


Result
+++++++++++++++


Single DataFrame with extra column sheet_name = "Jan", "Feb", etc.



Example 3 – Extract Only Named Table from Dashboard File
+++++++++++++++



Scenario
+++++++++++++++



Configuration
+++++++++++++++


* Path: s3://reports/dashboard_2024.xlsx
* Header Handling Mode: FIRST_ROW
* Enforce Schema: true (with predefined column names & types)


Result
+++++++++++++++


Clean, typed DataFrame containing only the intended table – ignores everything else.



Example 4 – Read Specific Range with Custom Multi-Row Header
+++++++++++++++



Scenario
+++++++++++++++

Header spans rows 3–5, data starts at row 6, only need columns B to P.



Configuration
+++++++++++++++


* Range: B6:P1000
* Start Data Import on Line: 6
* Header Handling Mode: CUSTOM_ROW
* Custom Header Row: 3:5
* Drop Special Character In Column Name: true


Result
+++++++++++++++


Proper multi-level column names (concatenated) and only the required columns.



Example 5 – Discover All Sheets in a New File
+++++++++++++++



Configuration
+++++++++++++++


* Path: /incoming/new_report.xlsx
* Import Only Sheet Names: true


Result
+++++++++++++++

::

    | sheet_name   |
    |--------------|
    | Cover        |
    | Summary      |
    | Raw Data     |
    | Pivot Tables |



Example 6 – Force Strict Schema (Finance Use Case)
+++++++++++++++



Scenario
+++++++++++++++


Excel files come from different regions with different header languages, but business needs consistent column names and types.



Configuration
+++++++++++++++


* Enforce Schema: true
* Output Column Names: ["Transaction_ID", "Date", "Amount", "Currency", "Region", "Category"]
* Output Column Types: ["string", "date", "double", "string", "string", "string"]
* Output Column Formats: ["", "dd-MM-yyyy", "", "", "", ""]


Result
+++++++++++++++


Every file outputs exactly the same schema regardless of original headers or formats.
