Save DOCX
===========

Saves DataFrame responses as DOCX files

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveDocx

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
        - Path where to save the DOCX files (local or S3)
      * - content
        - Content Column
        - DataFrame column containing content for output files
      * - saveMode
        - Save Mode
        - Whether to Append, Overwrite, Error if the path Exists, or Ignore
      * - System Prompt
        - Advanced
        - 
      * - generic_file_name
        - Default File Name
        - Default docx file name where the DOCX will be saved
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


Details
-------
Save DOCX Node Details
+++++++++++++++

The Save DOCX Node is designed to save DataFrame responses as DOCX files, either locally or to an S3 bucket. It supports saving content from a specified DataFrame column, with options to combine responses into a single file, save individual files, or group by page number. The node processes text or markdown content, converting it to DOCX format with proper formatting for headers, lists, and paragraphs. This node is ideal for generating structured DOCX outputs in data pipelines.



General:
+++++++++++++++


Output Path: Specifies the file path where the DOCX files will be saved. This can be a local path or an S3 path (e.g., s3://bucket_name/prefix/). This field is required.


Content Column: Specifies the DataFrame column containing the content to be saved as DOCX. This can include text or markdown content. This field is optional, but required if no default content is provided.


Save Mode: Determines the behavior when the output path already exists. Options are:


* Overwrite: Overwrites existing files at the specified path.
* ErrorIfExists: Throws an error if the output path already exists.
* Ignore: Skips saving if the output path already exists.


Default File Name: Specifies the default file name for the DOCX output (e.g., "docx_output"). Used when no file name column is provided or when saving a single combined file.


Save Option: Specifies how the responses are saved. Options are:


* ALL: Combines all responses into a single DOCX file.
* PERFILE: Saves each response as a separate DOCX file, based on the file name column.
* NONE: Saves each page as a separate DOCX file, grouped by page number.


File Name Column: Specifies the DataFrame column containing file names for the output DOCX files. This is required when Save Option is set to PERFILE or NONE.


Page Number Column: Specifies the DataFrame column containing page numbers for multi-page documents. This is required when Save Option is set to NONE.


Translate File Name: Determines whether non-English file names should be translated to English before saving. Options are:


* true: Translates file names to English using an external translation service (e.g., Google Translator).
* false: Retains original file names without translation.


System Prompt Configuration:
+++++++++++++++


System Prompt: An optional tab for advanced configurations. Currently, no specific system-level prompt is used, but this can be extended for future customization of DOCX generation behavior.



Output:
+++++++++++++++

The node does not modify the input DataFrame but saves the content from the specified column as DOCX files to the designated output path. The output DOCX files may include:


* A single combined DOCX file (if Save Option is ALL).
* Individual DOCX files for each response (if Save Option is PERFILE).
* Separate DOCX files for each page (if Save Option is NONE).
* The generated DOCX files include formatted text or markdown content, with proper styling for headers, bullet lists, and paragraphs.


Examples
-------
Example: Save DOCX Node
+++++++++++++++



Input:
+++++++++++++++

A DataFrame contains the following data:


* content: ["# Climate Change\\n- Rising sea levels\\n- Extreme weather", "#Renewable Energy\\nSolar and wind advancements...", "# AI Study\\n- Machine learning\\n- Neural networks"]
* fileName: ["climate_report", "energy_report", "ai_study"]
* pageNumber: [1, 1, 2]


The Save DOCX Node is configured as follows:


* Output Path: /data/output/docx/
* Content Column: content
* Save Mode: Overwrite
* Default File Name: docx_output
* Save Option: PERFILE
* File Name Column: fileName
* Page Number Column: pageNumber
* Translate File Name: false
* System Prompt: Empty (no advanced configuration used)


Output:
+++++++++++++++


The node processes the DataFrame and saves DOCX files to /data/output/docx/ with the following structure:



* climate_report.docx: Contains formatted content with a header "Climate Change" and a bullet list.
* energy_report.docx: Contains formatted text content with a paragraph for "Renewable Energy" and its description.
* ai_study.docx: Contains formatted content with a header "AI Study" and a bullet list.


Explanation:
+++++++++++++++

* The first row processes the markdown content "# Climate Change\\n- Rising sea levels\\n- Extreme weather", converting it to a DOCX file with a bold header and bullet points.
* The second row processes the plain text content "Renewable Energy\\nSolar and wind advancements...", saving it as a DOCX file with paragraphs.
* The third row processes the markdown content "# AI Study\\n- Machine learning\\n- Neural networks", converting it to a DOCX file with a bold header and bullet points.
* Since Save Option is set to PERFILE, each response is saved as a separate DOCX file named after the fileName column (e.g., climate_report.docx).
* The Page Number Column is used to track page numbers but does not affect the output since Save Option is PERFILE.
* Translate File Name is set to false, so file names are used as-is without translation.
* Save Mode is set to Overwrite, so any existing files in /data/output/docx/ are overwritten.
* The output DOCX files are saved to the local path /data/output/docx/ with proper formatting for headers, bullet lists, and text, using the python-docx library for DOCX generation.
