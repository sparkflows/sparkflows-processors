Interactive LLM Agent
===========

This node enables standalone or dataframe-optional LLM queries across multiple providers (OpenAI, Bedrock, Gemini). It is designed for sequential agent flows like 'Similar Company Finder' and supports saving structured responses.

Input
--------------
Optional DataFrame (if metadata columns are selected)

Output
--------------
Returns response as DataFrame

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeInteractiveLLMAgent

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
      * - customPrompt
        - Prompt
        - Custom prompt to instruct the model.
      * - metadataCols
        - Metadata Columns
        - Select one or more content columns to pass as input to the model.


Details
-------
Interactive LLM Agent Node Details
+++++++++++++++

The Interactive LLM Agent node enables querying large language models (LLMs) such as OpenAI, Bedrock (Anthropic), and Gemini from Google, using either a standalone prompt or content from a DataFrame. It is designed for flexible agent workflows and provides safe input and output validation.



General:
+++++++++++++++



Custom Prompt:
+++++++++++++++

This field lets you specify the user query or task description. If the node is used without a DataFrame, this prompt is the only content passed to the LLM.



Metadata Columns:
+++++++++++++++

When a DataFrame is passed into the node, you can select one or more content columns whose text will be sent to the LLM. The prompt and content will be combined and sent to the model.




Select Connection:
+++++++++++++++

Each model provider requires specific connection credentials (e.g., API keys). These must be configured in the backend and are referenced here.



Temperature, Max Tokens, and Retries:
+++++++++++++++

* **Temperature** controls creativity: lower values yield more deterministic outputs.
* **Max Tokens** sets the maximum length of the generated response.
* **Retries** determine how many times to retry in case of failure.



Output:
+++++++++++++++

The output is a Spark DataFrame with a single column:

* **response**: Contains the LLM-generated response, cleaned and validated.


If a DataFrame is passed in with metadata columns, their values are merged into the prompt. Otherwise, the prompt is used as-is.


Examples
-------
Example: Interactive LLM Agent Node
+++++++++++++++



Input:
+++++++++++++++

A DataFrame with the following data:

.. list-table::
      :widths: 10 10
      :header-rows: 1

      * - company_name
        - industry
      * - TechCorp
        - Software
      * - InnovateAI
        - Artificial Intelligence



Configuration:
+++++++++++++++

* **Custom Prompt:** "Find companies similar to {company_name} in the {industry} industry."
* **Metadata Columns:** [company_name, industry]
* **Temperature:** 0.7
* **Max Tokens:** 512
* **Retries:** 2



Output:
+++++++++++++++

A DataFrame with a single response column:

.. list-table::
      :widths: 10
      :header-rows: 1

      * - response
      * - TechCorp (Software): - CodeZap - SoftPeak - NexlifyInnovateAI (Artificial Intelligence): - AIWorks - NeuralNest - DeepMind



Explanation:
+++++++++++++++

* The node reads values from metadata columns and constructs a prompt for each row.
* The content and task are passed to the OpenAI LLM.
* The response is generated, cleaned of Markdown wrappers (e.g., ```json)
* The output is returned in a DataFrame as a single response string (across all rows).
