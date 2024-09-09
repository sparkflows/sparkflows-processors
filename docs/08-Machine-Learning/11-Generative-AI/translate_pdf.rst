Translate PDF
=========== 

Translates the pdf files from the input directory and outputs corresponding translated txt files in the output directory

Input
--------------
It takes in a DataFrame as input

Type
--------- 

dataset

Class
--------- 

fire.nodes.gai.NodeTranslatePdf

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputDirectoryPath
        - Path
        - Select a Pdf file
      * - separator
        - Separator
        - Enter a separator
      * - chunk_size
        - Chunk Size
        - Enter chunk size
      * - chunk_overlap
        - Chunk Overlap
        - Enter chunk overlap size
      * - language
        - Language
        - Language name 
      * - outputPath
        - Path
        - Select a path to save translated txt file
      * - advanced
        - LLM Connection
      * - llmConnection
        - Connection
        - The LLM connection to connect
      * - temperature
        - Temperature
        - What sampling temperature to use.
      * - model
        - Model
        - Model name to use.
      * - max_tokens
        - Max Tokens
        - Maximum number of tokens to generate.
      * - max_retries
        - Max Retries
        - Maximum number of retries to make when generating.
      * - n
        - N
        - Number of chat completions to generate for each prompt.
      * - streaming
        - streaming
        - Whether to stream the results or not
      * - OpenAI_organization
        - OpenAI Organization
        - OpenAI Organization
      * - OpenAI_proxy
        - OpenAI Proxy
        - OpenAI Proxy
      * - tiktoken_model_name
        - Tiktoken Model Name
        - The model name to pass to tiktoken




