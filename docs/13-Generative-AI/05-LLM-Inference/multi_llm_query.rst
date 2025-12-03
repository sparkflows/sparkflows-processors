Multi LLM Query
===========

The Multi LLM Query node is designed to query multiple large language models (LLMs) from providers such as OpenAI, Bedrock, and Gemini, using a DataFrame as input. It processes user queries, text content, and/or base64-encoded images to generate responses based on the selected model and task, producing a structured DataFrame output.

Input
--------------
It may take in Dataframe as an input

Output
--------------
Returns response as Dataframe

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeMultiLLMQuery

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
      * - temperature
        - Temperature
        - Temperature setting for the model (default: 0).
      * - contentCol
        - Content Column
        - Column name for the text content.
      * - imageCol
        - Image Column
        - Column name for the base 64 image.
      * - inputMode
        - Mode Selection
        - Select the model to use (text, image, text+image).
      * - Prompt
        - Prompt
        - 
      * - task
        - Select Prompt
        - Specify the task to perform: summary, translation, topic extraction, or other.
      * - customPrompt
        - Prompt
        - Custom prompt to override the default instructions.
      * - userQueryCol
        - User Query Column
        - Column name for user query, (if the query is in a column)
      * - Advanced
        - Advanced
        - 
      * - aggregateMode
        - Aggregate Response
        - 
      * - numPartitions
        - Number of Partitions
        - Number of Partitions
      * - fileNameCol
        - File Name Column
        - Select File Name Column
      * - pageNumberCol
        - Page Number Column
        - Select Page Number column.
      * - timeout
        - Timeout (seconds)
        - Maximum time to wait for Openai and Gemini API response
      * - thinkingBudget
        - Thinking Budget
        - Configure the Gemini thinking budget by specifying the number of tokens to allocate for thinking. For Flash and Flash Lite models, values can range from 0 to 24,576 or -1 for dynamic thinking. For 2.5 Pro model, values must be between 1 and 24,576; setting 0 is not allowed.


Details
-------
Multi LLM Query Node Details
+++++++++++++++


The Multi LLM Query node is designed to query multiple large language models (LLMs) from providers such as OpenAI, Bedrock, and Gemini, using a DataFrame as input. It processes user queries, text content, and/or base64-encoded images to generate responses based on the selected connection and task, producing a structured DataFrame output.



General:
+++++++++++++++



Select Task:
+++++++++++++++

Specifies the task to perform. Options include:


* summary: Generates a summary of the content in bullet points.
* translation: Translates the content to English.
* topic_extraction: Extracts key topics from the content.
* other: Allows for a custom task defined by the user.


Prompt:
+++++++++++++++


Allows users to provide a custom prompt / instructions for the selected task.



Content Column:
+++++++++++++++

Specifies the DataFrame column containing the text content to be processed. Required for text or text+image modes.



Select Connection:
+++++++++++++++

Specifies the connection details for the selected LLM provider (e.g., API keys for OpenAI/Gemini, AWS credentials for Bedrock). Required to authenticate and access the respective model.



Temperature:
+++++++++++++++

Controls the randomness of the LLM's output. Default is 0.7. Higher values increase creativity, while lower values ensure more deterministic responses.



Image Column:
+++++++++++++++

Specifies the DataFrame column containing base64-encoded images. Required for image or text+image modes.



Mode Selection:
+++++++++++++++

Determines the input mode for the LLM. Options are:


* text: Processes text-only input from the content column or custom prompt.
* image: Processes base64-encoded images from the image column.
* text+image: Processes both text and base64-encoded images.


Timeout (seconds):
+++++++++++++++


Specifies the maximum time (in seconds) to wait for the model response. Visible when OpenAI or Gemini is selected.



Thinking Budget:
+++++++++++++++

Controls the computational budget (e.g., steps or tokens) for Gemini models. Only visible when Gemini is selected.



Advanced:
+++++++++++++++



Aggregate Response:
+++++++++++++++

Specifies how to aggregate input data before processing. Options are:


* none: Processes each row individually, retaining fileName and pageNumber (if provided).
* all: Aggregates all rows into a single response.
* perfile: Aggregates rows by fileName, producing one response per file.


Number of Partitions:
+++++++++++++++


Specifies the number of Spark partitions for distributed processing. Default is 3.



File Name Column:
+++++++++++++++

Specifies the DataFrame column containing file names. Required for perfile aggregation mode.



Page Number Column:
+++++++++++++++

Specifies the DataFrame column containing page numbers (e.g., for PDFs). Optional, used for row-wise processing with none aggregation mode.



Output:
+++++++++++++++

The node outputs a DataFrame with columns based on the aggregation mode:


* none: Includes fileName (if provided), pageNumber (if provided), and response.
* perfile: Includes fileName and response.
* all: Includes only the response column.

The response column contains the LLM-generated text or error messages if the API call fails.


Examples
-------
Multi LLM Query Node Examples
+++++++++++++++



Input:
+++++++++++++++

A DataFrame contains the following data:


* fileName: ["doc1.pdf", "doc1.pdf", "doc2.pdf"]
* pageNumber: ["1", "2", null]
* content: ["Article about climate change...", "Climate change impacts...", "Renewable energy report..."]
* imageBase64: [null, "iVBORw0KGgoAAAANSUhEUg...", null]


The Multi LLM Query node is configured as follows:


* Select Task: summary
* Prompt: "Summarize the content in bullet points."
* Content Column: content
* Select Connection: Configured with valid OpenAI API key
* Temperature: 0.7
* Timeout (seconds): 90
* Image Column: imageBase64
* Mode Selection: text+image
* Aggregate Response: perfile
* Number of Partitions: 3
* File Name Column: fileName
* Page Number Column: pageNumber


Output:
+++++++++++++++


The node processes the DataFrame and produces a DataFrame with the following structure:


* fileName: doc1.pdf

response:


* Climate change effects on ecosystems
* Rising temperatures

* fileName: doc2.pdf

response:


* Renewable energy advancements
* Solar and wind adoption
