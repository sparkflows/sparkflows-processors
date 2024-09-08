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




