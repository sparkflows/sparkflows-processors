Video Summarization
=========== 

This process involves creating text summary for the video.

Input
--------------
It takes in video file path as an input

Output
--------------
Summary in a text file

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeVideoSummarization

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - llmConnection
        - Select Connection
        - Select Connection
      * - videoFilePath
        - Select video path
        - Select Video File path
      * - summaryLength
        - Select summary length
        - Select the number of words the summary should be generated
      * - language
        - Select language
        - Select the language the summary should be generated in.
      * - saveOutputPath
        - Output path
        - The path where the txt file will be saved.


Details
-------
Video Summarization Node Details
---------------

The Video Summarization node processes video files to generate a text summary of their content. It leverages a large language model (LLM) to analyze the video and produce a concise summary, which is saved as a text file at the specified output path. This node is designed for PySpark-based workflows, making it suitable for automated video content analysis in data pipelines.



General:
+++++++++++++++



Select Connection: Specifies the connection details for the LLM (e.g., API key for the selected provider). This is required to authenticate and access the model used for summarization.
+++++++++++++++



Select Video Path: Specifies the file path to the video file to be summarized. This field is required and must point to a valid video file accessible to the PySpark engine.
+++++++++++++++



Select Summary Length: Specifies the desired number of words for the generated summary. This is optional; if left empty, the LLM uses a default length determined by the model.
+++++++++++++++



Select Language: Specifies the language in which the summary should be generated. This is optional; if left empty, the default language (typically English) is used by the LLM.
+++++++++++++++



Output Path: Specifies the file path where the generated summary will be saved as a .txt file. This is optional; if provided, the summary is saved to the specified location.
+++++++++++++++



Output:
+++++++++++++++

The node outputs the generated summary as a text file saved at the specified Output Path. The summary contains a concise description of the video content, formatted as plain text in the chosen language and adhering to the specified word count if provided.


Examples
-------
Example: Video Summarization Node
---------------



Input:
+++++++++++++++

A video file is located at:


* /data/videos/product_demo.mp4 (a 3-minute video demonstrating a new software product)


The Video Summarization node is configured as follows:


* Select Connection: Configured with a valid LLM API key (e.g., OpenAI)
* Select Video Path: /data/videos/product_demo.mp4
* Select Summary Length: 100
* Select Language: en
* Output Path: /data/output/summary.txt


Output:
+++++++++++++++


The node processes the video file and generates a text file at /data/output/summary.txt with the following content:


* The video showcases a new software product, highlighting its user-friendly interface, key features like real-time analytics and collaboration tools, and its benefits for improving team productivity. The demo includes a walkthrough of the dashboard and integration capabilities.


Explanation:
+++++++++++++++

* The product_demo.mp4 file is processed using the specified LLM connection to analyze its content and generate a summary.
* The Select Summary Length is set to 100 words, ensuring the summary is concise and approximately 100 words long.
* The Select Language is set to 'en' (English), so the summary is generated in English.
* The summary is saved as a .txt file at /data/output/summary.txt as specified in the Output Path.
* If Select Summary Length was left empty, the LLM would determine an appropriate length for the summary.
* If Select Language was left empty, the default language (English) would be used by the LLM.
