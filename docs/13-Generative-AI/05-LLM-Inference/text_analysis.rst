Text Analysis
=========== 



Input
--------------
It takes directory or path as an input

Output
--------------
Outputs a Dataframe with 2 columns speaker and dialouge

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeTextAnalysis

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - isWordCloud
        - Word Cloud
        - Render Word cloud chart
      * - selectedAnalysis
        - Analysis Type
        - Analysis Type
      * - openai
        - OpenAI
        - 
      * - llmConnection
        - Select Connection
        - Select Connection
      * - openaiModel
        - OpenAI Model
        - OpenAI Model to be Used


Details
===============
Text Analysis Node Details
---------------

The Text Analysis node processes text data to perform various types of analysis, such as tone, emotion, sentiment, or slang analysis, using an OpenAI model. It takes a directory or file path as input and generates a structured DataFrame output. Optionally, it can render a word cloud chart to visualize the text data. This node is designed for PySpark-based workflows, making it suitable for advanced text analysis in data pipelines.



General:
+++++++++++++++



Word Cloud: Controls whether a word cloud chart is rendered to visualize the text data. Options are:
+++++++++++++++


* true: Generates a word cloud chart based on the input text (default).
* false: Does not generate a word cloud chart.


Analysis Type: Specifies the type of text analysis to perform. This field is required. Options include:
+++++++++++++++

* TONE ANALYSIS: Analyzes the tone of the text (e.g., formal, informal, positive, negative).
* EMOTION ANALYSIS: Identifies emotions expressed in the text (e.g., joy, anger, sadness).
* SENTIMENT ANALYSIS: Determines the sentiment of the text (e.g., positive, negative, neutral).
* SLANG ANALYSIS: Detects and analyzes slang or informal language in the text.


OpenAI Configuration:
+++++++++++++++



Select Connection: Specifies the connection details for the OpenAI API (e.g., API key). This is required to authenticate and access the OpenAI model.
+++++++++++++++



OpenAI Model: Specifies the OpenAI model to use for text analysis. Default is 'gpt-4o'. This field is required, and other compatible models can be specified if supported by the OpenAI API.
+++++++++++++++



Output:
+++++++++++++++


The node outputs a DataFrame with two columns:


* speaker: The identifier for the text source (e.g., speaker label or file name, depending on input).
* dialogue: The result of the specified analysis (e.g., tone, emotion, sentiment, or slang details).

If Word Cloud is set to true, a word cloud chart is also generated to visualize the frequency or significance of words in the input text.


Examples
===============
Example: Text Analysis Node
---------------



Input:
+++++++++++++++

A text file is located at:


* /data/text/conversation.txt (containing a dialogue: "I'm so excited about the new project! It's going to be awesome!")


The Text Analysis node is configured as follows:


* Word Cloud: true
* Analysis Type: SENTIMENT ANALYSIS
* Select Connection: Configured with a valid OpenAI API key
* OpenAI Model: gpt-4o


Output:
+++++++++++++++


The node processes the text file and produces a DataFrame with the following structure:


::

    speaker         | dialogue
    ----------------|----------------------------
    conversation.txt| Positive sentiment detected


Additionally, a word cloud chart is generated, highlighting words like "excited," "new," "project," and "awesome" based on their frequency and significance.



Explanation:
+++++++++++++++


* The conversation.txt file is processed using the OpenAI gpt-4o model for SENTIMENT ANALYSIS.
* The Analysis Type is set to SENTIMENT ANALYSIS, so the node evaluates the text and determines it has a positive sentiment, which is output in the dialogue column.
* The speaker column contains the file name (conversation.txt) as the identifier for the text source.
* With Word Cloud set to true, a word cloud chart is generated, visually representing the most prominent words in the input text.
* If Analysis Type was set to TONE ANALYSIS, the output might describe the tone (e.g., "Enthusiastic tone detected").
* If Word Cloud was set to false, no word cloud chart would be generated.
