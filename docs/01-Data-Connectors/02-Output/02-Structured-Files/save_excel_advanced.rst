Save Excel Advanced
=========== 

Powerful Excel Writer Node – Export DataFrames to .xlsx files with full control over sheets, ranges, dynamic naming, record splitting, formatting preservation, password protection, and advanced save modes. Ideal for business reporting, finance dashboards, compliance exports, and audit-ready files.

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveExcelAdvanced

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - path
        - Path / File
        - Full destination path including file name. Supports local, HDFS, S3, GCS, ADLS, etc. Example: /output/reports/sales_2024.xlsx or s3a://reports/final_output.xlsx
      * - saveMode
        - Save Mode
        - How to handle existing files/sheets: • OverwriteFile → replaces entire workbook • OverwriteSheet → replaces only the target sheet (keeps other sheets) • AppendSheet → adds rows below existing data • ErrorIfExists → fails if file already exists • Ignore → silently skips writing if file exists
      * - sheetName
        - Sheet Name
        - Name of the sheet to create or write to. Can be static (e.g., Summary) or dynamically generated via 'Sheet Name / File From Field'.
      * - range
        - Range
        - Optional A1-style range or starting cell: • C10 → starts writing at cell C10 (great for templates) • B5:G50 → writes only inside this rectangle (truncates excess rows/cols) Required when Preserve Formatting = true.
      * - takeNameFromField
        - Sheet Name / File From Field
        - Column name to use for dynamic output: • If value exists in a row → creates one sheet per unique value (e.g., Region → sheets North, South, etc.) • If column has only one distinct value → can also be used to name the entire file dynamically
      * - includeHeader
        - Include Header Row
        - Write column names as the first row in Excel. Usually set to true for reporting.
      * - preserveFormatting
        - Preserve Formatting
        - Keep existing cell styles (fonts, colors, borders, number formats) when overwriting a range or sheet. Requires a defined Range and OverwriteSheet mode. Perfect for pre-formatted report templates.
      * - suppressIfNoRecords
        - Suppress Output if No Records
        - Do not create any file/sheet if the DataFrame is empty. Prevents empty placeholder files in production.
      * - maxRecordsPerSheet
        - Max Records Per Sheet
        - Maximum rows (excluding header) per sheet. If exceeded, automatically creates Sheet1_1, Sheet1_2, etc. Set to 0 for unlimited (default Excel limit ~1M rows).
      * - maxRecordsPerFile
        - Max Records Per File
        - Maximum total rows per output file. If exceeded, creates part files: report.xlsx, report_0001.xlsx, report_0002.xlsx, etc. Set to 0 for no splitting.
      * - password
        - Password
        - Optional password to protect the entire workbook or specific sheet. Users will need the password to open or modify the file.
      * - boxConnection
        - Box Connection
        - 
      * - accessToken
        - Access Token
        - 


Details
===============
Save Excel Advanced Node – Complete Business-Ready Guide
---------------

The Save Excel Advanced node is the most feature-rich Excel writer available. It turns any Spark DataFrame into beautiful, audit-ready, pre-formatted Excel reports — exactly the way finance, compliance, and business teams expect them.



Perfect For
+++++++++++++++


* Monthly/quarterly financial reports using corporate templates
* Regulatory exports that must preserve formatting
* Distributing one file per region/department automatically
* Avoiding 1-million-row Excel limits by auto-splitting
* Secure distribution of sensitive data via password protection
* Replacing manual “copy-paste into template” work


Key Capabilities
+++++++++++++++

* Write to exact cell (e.g., drop data into C10 of a pre-built dashboard)
* Preserve all existing formatting when updating templates
* Dynamic sheet creation (one sheet per Region, Product, Month, etc.)
* Automatic sheet & file splitting for huge datasets
* Five intelligent save modes (including AppendSheet)
* Password-protected workbooks
* Full distributed filesystem support (S3, ADLS, GCS, HDFS)


Core Parameters Explained
+++++++++++++++



Save Mode + Preserve Formatting + Range → The “template update” superpower
+++++++++++++++


Use OverwriteSheet + a defined Range + Preserve Formatting = true to drop fresh numbers into a beautifully formatted corporate template without breaking anything.



Take Name From Field
+++++++++++++++

The fastest way to create “one sheet per category” reports. Just point to a column (e.g., Country, Department, YearMonth) and the node does the rest.



Max Records Per Sheet / Per File
+++++++++++++++

Excel has hard limits (~1,048,576 rows). These options automatically split large exports safely and predictably.



Suppress If No Records
+++++++++++++++

Critical in scheduled pipelines — no embarrassing empty files sent to executives.


Examples
===============
Save Excel Advanced – Real Business Scenarios
---------------



Example 1 – Update Pre-Formatted Monthly Report Template
+++++++++++++++



Scenario
+++++++++++++++

You have a beautiful template “Monthly_Report_Template.xlsx” with logos, colors, charts, and an empty table starting at B10.



Configuration
+++++++++++++++


* Path: s3://reports/Monthly_Report_Nov2025.xlsx
* Save Mode: OverwriteSheet
* Sheet Name: Data
* Range: B10
* Preserve Formatting: true
* Include Header: true


Result
+++++++++++++++


Only the data area is refreshed — logos, charts, conditional formatting, and print settings remain untouched.



Example 2 – One Sheet Per Region (Most Popular Use Case)
+++++++++++++++



Configuration
+++++++++++++++


* Path: /output/2025_Sales_By_Region.xlsx
* Save Mode: OverwriteFile
* Take Name From Field: Region
* Include Header: true


Result
+++++++++++++++


One workbook with sheets automatically named: NorthAmerica, EMEA, APAC, LATAM — each containing only its region’s data.



Example 3 – Append Daily Data to Growing Sheet
+++++++++++++++



Configuration
+++++++++++++++


* Path: /audit/daily_transactions.xlsx
* Save Mode: AppendSheet
* Sheet Name: Transactions
* Include Header: false (header already exists)


Result
+++++++++++++++


New rows are added below yesterday’s data — perfect for incremental logs.



Example 4 – Auto-Split Huge Export (5 Million Rows)
+++++++++++++++



Configuration
+++++++++++++++


* Path: /output/all_customers.xlsx
* Max Records Per Sheet: 900000
* Max Records Per File: 2000000


Result
+++++++++++++++


Creates:

all_customers.xlsx        (first 2M rows, split into 3 sheets)

all_customers_0001.xlsx   (next 2M rows)

all_customers_0002.xlsx   (remaining rows)



Example 5 – Secure Compliance Export
+++++++++++++++



Configuration
+++++++++++++++


* Path: /secure/employee_salary_data.xlsx
* Sheet Name: Salaries
* Password: P@ssw0rd2025!
* Include Header: true
* Suppress If No Records: true


Result
+++++++++++++++


Password-protected workbook. If query returns zero rows → no file is created.



Example 6 – Dynamic File Name from Data + Multiple Sheets
+++++++++++++++



Data contains column ReportMonth = "2025-11"
+++++++++++++++



Configuration
+++++++++++++++


* Path: /reports/Sales_${ReportMonth}.xlsx  (or use Take Name From Field for file naming if supported)
* Take Name From Field: Department
* Include Header: true


Result
+++++++++++++++


File created as Sales_2025-11.xlsx containing sheets HR, IT, Finance, Marketing, etc.
