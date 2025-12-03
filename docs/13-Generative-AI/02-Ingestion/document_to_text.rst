Document To Text
===========

The DocumentToText node extracts text content from documents, including PDF, TXT, DOCX, and image files, located in a specified file path or directory. It processes either a single file or an entire directory, producing a structured DataFrame with columns for the extracted text, file name, page numbers, and optionally, base64-encoded data for PDFs and images.

Input
--------------
It takes directory or path as an input

Output
--------------
Outputs a Dataframe with page content and file name columns

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeDocumentToText

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - filePath
        - Directory/File Path
        - Select a Pdf/Docx/Images File or Directory
      * - fileType
        - Document Type
        - Choose a Document Type.If Empty all three types of files will be processed.
      * - recursive
        - Recursive
        - Recursively process the documents in the given Directory
      * - isImage
        - Image Encoding
        - Adds a column for base64 encoded pages
      * - columns
        - Rename Output Cols
        - 
      * - fileNameCol
        - File Name Column
        - Rename File Name Column. Defaults to fileName
      * - contentCol
        - Content Column
        - Rename Content Column. Defaults to content
      * - pageNumberCol
        - Page Number Column
        - Rename Page Number Column. Defaults to pageNumber
      * - base64ImageCol
        - Base64 Image Column
        - Rename Image Column. Defaults to base64ImageCol


Details
-------
DocumentToText Node Details
+++++++++++++++

The DocumentToText node extracts text content from documents, including PDF, DOCX, and image files, located in a specified file path or directory. It processes either a single file or an entire directory, producing a structured DataFrame with columns for the extracted text, file name, page numbers, and optionally, base64-encoded data for PDFs and images.




General:
+++++++++++++++


Directory/File Path: Specifies the path to a single document file or a directory containing multiple documents. This field is required and must be accessible to the PySpark engine.


Document Type: Selects the types of documents to process. Options include:



* pdf: Processes PDF files, extracting text and optionally converting pages to base64-encoded images.
* docx: Processes Microsoft Word documents, extracting text only.
* image: Processes image files (e.g., PNG, JPEG) for text extraction via OCR, with optional base64 encoding.


If left empty, the node processes all supported file types (PDF, DOCX, and images) in the specified path.



Image Encoding: Determines whether to include a column with base64-encoded data for PDFs and images. Options are:


* true: Adds a column with base64-encoded representations of PDF pages and image files.
* false: Does not include base64-encoded data (default).


Note: TXT and DOCX files are not converted to base64 encodings, even if this option is enabled.




Recursive Processing:
+++++++++++++++

Recursive: Controls whether the node processes documents in subdirectories. Options are:


* true: Recursively processes all documents in the specified directory and its subdirectories.
* false: Processes only documents directly in the specified directory (default).



Output Storage:
+++++++++++++++



Output:
+++++++++++++++


The node outputs a DataFrame with the following default columns:



* fileName: The name of the source file.
* content: The extracted text content from the document.
* pageNumber:> The page number of the extracted content (for multi-page documents like PDFs; single-page documents like TXT, DOCX, and images use page number 1).
* If Image Encoding is set to true, a base64ImageData column is included for PDFs and images, containing base64-encoded representations of the pages or images. TXT and DOCX files will have null in this column.


Examples
-------
Example: DocumentToText Node
+++++++++++++++



Input:
+++++++++++++++

A directory /data/documents/ contains the following files:


* report.pdf (a 2-page PDF document)
* proposal.docx (a Microsoft Word document)
* chart.png (an image file with text)


The DocumentToText node is configured as follows:


* Directory/File Path: /data/documents/
* Document Type: ["pdf", "docx", "image"] (process all supported types)
* Image Encoding: true (includes base64-encoded data for PDFs and images)
* Recursive: false (processes only files in the specified directory)


Output:
+++++++++++++++


The node processes the files and produces a DataFrame with the following structure:


::

    fileName       | content                              | pageNumber | base64ImageData
    ---------------|--------------------------------------|------------|----------------------------------
    report.pdf     | This is page 1 of the report...      | 1          | iVBORw0KGgoAAAANSUhEUg...
    report.pdf     | This is page 2 of the report...      | 2          | iVBORw0KGgoAAAANSUhEUg...
    proposal.docx  | Proposal for new project...          | 1          | null
    chart.png      | Sales: Q1 2025...                    | 1          | iVBORw0KGgoAAAANSUhEUg...



Explanation:
+++++++++++++++


* The report.pdf file is processed, extracting text from both pages, resulting in two rows (one per page). With Image Encoding set to true, each page is also converted to a base64-encoded image in the base64ImageData column.
* The proposal.docx file is processed, extracting its text content into a single row. No base64 encoding is applied, so base64ImageData is null.
* The chart.png file is processed using OCR to extract text, and its base64-encoded image data is included in the base64ImageData column.
* Since Recursive is set to false, only files directly in /data/documents/ are processed.
