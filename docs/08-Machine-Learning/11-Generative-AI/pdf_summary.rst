Summarize PDF
=========== 

Summarises Pdf Documents

Input
--------------
It takes in a DataFrame as input

Output
--------------
outputs a text file or a directory with summary text files

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodePdfSummary

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputFilePath
        - Path
        - Enter file path. Supported types: .pdf,.json, .txt, .docx
      * - outputPath
        - Path
        - Select a path to save pickle file
      * - separator
        - Separator
        - Enter a separator. If Empty defaults to recursive text splitter.
      * - chunk_size
        - Chunk Size
        - Enter chunk size
      * - chunk_overlap
        - Chunk Overlap
        - Enter chunk overlap size
      * - chain_type
        - Chain Type
        - Type of document combining chain to use
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
      * - top_p
        - Top_P
        - Total probability mass of tokens to consider at each step.
      * - frequency_penalty
        - Frequency Penalty
        - Penalizes repeated tokens according to frequency.
      * - presence_penalty
        - Presence Penalty
        - Penalizes repeated tokens.
      * - max_retries
        - Max Retries
        - Maximum number of retries to make when generating.
      * - best_of
        - Best of
        - Generates best_of completions server-side and returns the "best"
      * - n
        - N
        - How many completions to generate for each prompt.
      * - max_tokens
        - Max Tokens
        - The maximum number of tokens to generate in the completion
      * - OpenAI_organization
        - OpenAI Organization
        - OpenAI Organization
      * - tiktoken_model_name
        - Tiktoken Model Name
        - The model name to pass to tiktoken




