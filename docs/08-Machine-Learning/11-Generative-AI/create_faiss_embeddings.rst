Create Faiss Embeddings
=========== 

Creates Vector Embeddings, stores them in faiss db and save as a pickle file

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeCreateFaissEmbeddings

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputFilePath
        - Path Of Input File
        - Enter file path. Supported types: .pdf,.json, .txt, .docx
      * - outputPath
        - Path Of Vector DB
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
      * - column_name
        - Target Column
        - Target column for dataframe
      * - advanced
        - LLM Connection
      * - llmConnection
        - Connection
        - The LLM connection to connect
      * - model
        - Model
        - Model name to use.
      * - max_retries
        - Max Retries
        - Maximum number of retries to make when generating.
      * - embedding_ctx_length
        - Embedding ctx length
        - Embedding context length.
      * - OpenAI_organization
        - OpenAI Organization
        - OpenAI Organization
      * - tiktoken_model_name
        - Tiktoken Model Name
        - The model name to pass to tiktoken




