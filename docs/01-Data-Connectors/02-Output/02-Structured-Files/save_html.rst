Save HTML
=========== 

Saves DataFrame responses as HTML files

Type
--------- 

transform

Class
--------- 

fire.nodes.save.NodeSaveHtml

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
        - Path where to save the HTML files (local or S3)
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
        - Default html file name where the HTML will be saved
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
===============
Save HTML Node Details
---------------

The Save HTML Node is designed to save DataFrame responses as HTML files, either locally or to an S3 bucket. It supports saving content from a specified DataFrame column, with options to combine responses into a single file, save individual files, or group by page number. The node processes text, HTML, or markdown content, converting it to HTML format with proper styling. This node is ideal for generating structured HTML outputs in data pipelines.



General:
+++++++++++++++



Output Path: Specifies the file path where the HTML files will be saved. This can be a local path or an S3 path (e.g., s3://bucket_name/prefix/). This field is required.
+++++++++++++++



Content Column: Specifies the DataFrame column containing the content to be saved as HTML. This can include text, HTML, or markdown content. This field is optional, but required if no default content is provided.
+++++++++++++++



Save Mode: Determines the behavior when the output path already exists. Options are:
+++++++++++++++


* Overwrite: Overwrites existing files at the specified path.
* ErrorIfExists: Throws an error if the output path already exists.
* Ignore: Skips saving if the output path already exists.


Default File Name: Specifies the default file name for the HTML output (e.g., "html_output"). Used when no file name column is provided or when saving a single combined file.
+++++++++++++++



Save Option: Specifies how the responses are saved. Options are:
+++++++++++++++

* ALL: Combines all responses into a single HTML file.
* PERFILE: Saves each response as a separate HTML file, based on the file name column.
* NONE: Saves each page as a separate HTML file, grouped by page number.


File Name Column: Specifies the DataFrame column containing file names for the output HTML files. This is required when Save Option is set to PERFILE or NONE.
+++++++++++++++



Page Number Column: Specifies the DataFrame column containing page numbers for multi-page documents. This is required when Save Option is set to NONE.
+++++++++++++++



Translate File Name: Determines whether non-English file names should be translated to English before saving. Options are:
+++++++++++++++

* true: Translates file names to English using an external translation service (e.g., Google Translator).
* false: Retains original file names without translation.


System Prompt Configuration:
+++++++++++++++



System Prompt: An optional tab for advanced configurations. Currently, no specific system-level prompt is used, but this can be extended for future customization of HTML generation behavior.
+++++++++++++++



Output:
+++++++++++++++


The node does not modify the input DataFrame but saves the content from the specified column as HTML files to the designated output path. The output HTML files may include:


* A single combined HTML file (if Save Option is ALL).
* Individual HTML files for each response (if Save Option is PERFILE).
* Separate HTML files for each page (if Save Option is NONE).
* The generated HTML files include formatted text, HTML, or markdown content, with proper styling for headers, lists, and paragraphs.


Examples
===============
Example: Save HTML Node
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* content: ["# Climate Change\\n- Rising sea levels\\n- Extreme weather", "<html><body>Renewable Energy<p>Solar and wind advancements...</p></body></html>", "AI Study\\n- Machine learning\\n- Neural networks"]
* fileName: ["climate_report", "energy_report", "ai_study"]
* pageNumber: [1, 1, 2]


The Save HTML Node is configured as follows:


* Output Path: /data/output/htmls/
* Content Column: content
* Save Mode: Overwrite
* Default File Name: html_output
* Save Option: PERFILE
* File Name Column: fileName
* Page Number Column: pageNumber
* Translate File Name: false
* System Prompt: Empty (no advanced configuration used)


Output:
+++++++++++++++


The node processes the DataFrame and saves HTML files to /data/output/htmls/ with the following structure:



* climate_report.html: Contains formatted content with a header "Climate Change" and a bullet list.
* energy_report.html: Contains formatted HTML content with a header "Renewable Energy" and a paragraph.
* ai_study.html: Contains formatted content with a header "AI Study" and a bullet list.


Explanation:
+++++++++++++++

* The first row processes the markdown content "# Climate Change\\n- Rising sea levels\\n- Extreme weather", converting it to an HTML file with a bold header and bullet points.
* The second row processes the HTML content, saving it directly as an HTML file with proper formatting for the header and paragraph.
* The third row processes the markdown content "AI Study\\n- Machine learning\\n- Neural networks", converting it to an HTML file with a bold header and bullet points.
* Since Save Option is set to PERFILE, each response is saved as a separate HTML file named after the fileName column (e.g., climate_report.html).
* The Page Number Column is used to track page numbers but does not affect the output since Save Option is PERFILE.
* Translate File Name is set to false, so file names are used as-is without translation.
* Save Mode is set to Overwrite, so any existing files in /data/output/htmls/ are overwritten.
* The output HTML files are saved to the local path /data/output/htmls/ with proper formatting for headers, lists, and text, using markdown-to-HTML conversion for markdown content.
