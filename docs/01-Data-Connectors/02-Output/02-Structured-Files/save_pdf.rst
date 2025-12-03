Save PDF
===========

Saves DataFrame responses as PDF files

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSavePdf

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputPath
        - Output Path
        - Path where to save the PDF files (local or S3)
      * - content
        - Content Column
        - DataFrame column containing filenames for output files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite, Error if the path Exists, or Ignore
      * - System Prompt
        - Advanced
        - 
      * - generic_file_name
        - Default File Name
        - Default pdf file name where the PDF will be saved
      * - saveOption
        - Save Option
        - 
      * - fileNameCol
        - File Name Column
        - DataFrame column containing filenames for output files (used in separate files or page number modes)
      * - pageNumberCol
        - Page Number Column
        - DataFrame column containing page numbers for multi-page documents (used in page number mode)
      * - translateFileName
        - Translate File Name
        - Translates file names to be saved from any language to English
      * - enableDownloadLink
        - Enable Download Link
        - Generate download links for the saved PDF files


Details
-------
Save PDF Node Details
+++++++++++++++

The Save PDF Node is designed to save DataFrame responses as PDF files, either locally or to an S3 bucket. It supports saving content from a specified DataFrame column, with options to combine responses into a single file, save individual files, or group by page number. The node processes text, HTML, or markdown content, converting it to PDF format using libraries like WeasyPrint and FPDF. This node is ideal for generating structured PDF outputs in data pipelines.



General:
+++++++++++++++



Output Path: Specifies the file path where the PDF files will be saved. This can be a local path or an S3 path (e.g., s3://bucket_name/prefix/). This field is required.
+++++++++++++++



Content Column: Specifies the DataFrame column containing the content to be saved as PDF. This can include text, HTML, or markdown content. This field is optional, but required if no default content is provided.
+++++++++++++++



Save Mode: Determines the behavior when the output path already exists. Options are:
+++++++++++++++


* Overwrite: Overwrites existing files at the specified path.
* ErrorIfExists: Throws an error if the output path already exists.
* Ignore: Skips saving if the output path already exists.


Default File Name: Specifies the default file name for the PDF output (e.g., "pdf_output"). Used when no file name column is provided or when saving a single combined file.
+++++++++++++++



Save Option: Specifies how the responses are saved. Options are:
+++++++++++++++

* ALL: Combines all responses into a single PDF file.
* PERFILE: Saves each response as a separate PDF file, based on the file name column.
* NONE: Saves each page as a separate PDF file, grouped by page number.


File Name Column: Specifies the DataFrame column containing file names for the output PDF files. This is required when Save Option is set to PERFILE or NONE.
+++++++++++++++



Page Number Column: Specifies the DataFrame column containing page numbers for multi-page documents. This is required when Save Option is set to NONE.
+++++++++++++++



Translate File Name: Determines whether non-English file names should be translated to English before saving. Options are:
+++++++++++++++

* true: Translates file names to English using an external translation service (e.g., Google Translator).
* false: Retains original file names without translation.


System Prompt Configuration:
+++++++++++++++



System Prompt: An optional tab for advanced configurations. Currently, no specific system-level prompt is used, but this can be extended for future customization of PDF generation behavior.
+++++++++++++++



Output:
+++++++++++++++


The node does not modify the input DataFrame but saves the content from the specified column as PDF files to the designated output path. The output PDF files may include:


* A single combined PDF file (if Save Option is ALL).
* Individual PDF files for each response (if Save Option is PERFILE).
* Separate PDF files for each page (if Save Option is NONE).
* The generated PDFs may include formatted text, HTML, or markdown content, with proper styling for headers, lists, and paragraphs.


Examples
-------
Example: Save PDF Node
+++++++++++++++



Input:
+++++++++++++++

A DataFrame contains the following data:


* content: ["# Climate Change\\n- Rising sea levels\\n- Extreme weather", "<html><body>Renewable Energy<p>Solar and wind advancements...</p></body></html>", "AI Study\\n- Machine learning\\n- Neural networks"]
* fileName: ["climate_report", "energy_report", "ai_study"]
* pageNumber: [1, 1, 2]


The Save PDF Node is configured as follows:


* Output Path: /data/output/pdfs/
* Content Column: content
* Save Mode: Overwrite
* Default File Name: pdf_output
* Save Option: PERFILE
* File Name Column: fileName
* Page Number Column: pageNumber
* Translate File Name: false
* System Prompt: Empty (no advanced configuration used)


Output:
+++++++++++++++


The node processes the DataFrame and saves PDF files to /data/output/pdfs/ with the following structure:



* climate_report.pdf: Contains formatted content with a header "Climate Change" and a bullet list.
* energy_report.pdf: Contains formatted HTML content with a header "Renewable Energy" and a paragraph.
* ai_study.pdf: Contains formatted content with a header "AI Study" and a bullet list.


Explanation:
+++++++++++++++

* The first row processes the markdown content "# Climate Change\\n- Rising sea levels\\n- Extreme weather", converting it to a PDF with a bold header and bullet points.
* The second row processes the HTML content, rendering it directly as a PDF with proper formatting for the header and paragraph.
* The third row processes the markdown content "AI Study\\n- Machine learning\\n- Neural networks", converting it to a PDF with a bold header and bullet points.
* Since Save Option is set to PERFILE, each response is saved as a separate PDF file named after the fileName column (e.g., climate_report.pdf).
* The Page Number Column is used to track page numbers but does not affect the output since Save Option is PERFILE.
* Translate File Name is set to false, so file names are used as-is without translation.
* Save Mode is set to Overwrite, so any existing files in /data/output/pdfs/ are overwritten.
* The output PDFs are saved to the local path /data/output/pdfs/ with proper formatting for headers, lists, and text, using WeasyPrint for HTML/markdown content and FPDF for plain text.
