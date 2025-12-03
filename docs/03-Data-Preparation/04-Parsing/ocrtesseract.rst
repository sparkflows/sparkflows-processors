OCR
=========== 

Performs Optical Character Recognition using the Tesseract Library. Please make sure the TESSDATA_PREFIX environment variable is set to the parent directory of your 'tessdata' directory. Download the tessdata directory with git clone https://github.com/tesseract-ocr/tessdata.git

Type
--------- 

transform

Class
--------- 

fire.nodes.ocr.NodeOCRTesseract

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - imageNameCol
        - Image Name Column
        - input image column name
      * - imageCol
        - Image Column
        - input image column name
      * - outputCol
        - Output OCR Column
        - output column name


Details
===============
Model OCR Extract Node
---------------


This node extracts text from images using an OCR (Optical Character Recognition) model. It takes an image as input and outputs the extracted text as a string.


Examples
===============
Model OCR Extract Node Example
---------------


Given the following dataset:


::

    | ImageColumn |
    |---|---|
    | [image data] |


If you configure the Model OCR Extract node to extract text from the ImageColumn, the output would look like this:


ImageColumn    OutputOCRColumn

[image data]    "This is the extracted text from the image."
