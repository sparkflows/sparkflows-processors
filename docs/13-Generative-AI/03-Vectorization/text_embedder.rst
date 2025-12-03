Create Text Embedding
=========== 

This node enables the creation of a embedding text data and output as dataframe

Input
--------------
It takes in Dataframe as an input

Output
--------------
Output as dataframe which have extra embedding columns

Type
--------- 

transform

Class
--------- 

fire.nodes.gai.NodeTextEmbedder

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - createEmbedding
        - Create Embedding
        - 
      * - embeddingMethod
        - Embedding Method
        - Select the embedding method.
      * - llmConnection
        - Select Connection
        - Select Connection
      * - chunkSize
        - Chunk Size
        - Size of each text chunk.
      * - chunkOverlap
        - Chunk Overlap
        - Overlap size between consecutive chunks.
      * - contentCol
        - Vector Indexer
        - Column name for content.
      * - queryEmbedding
        - Query Embedding
        - 
      * - userQuery
        - User Query
        - User provided query.
      * - huggingface
        - Hugging Face
        - 
      * - hfModelName
        - Hugging Face Model
        - Hugging Face embedding model.


Details
-------
Text Embedder Node Details
---------------


This node enables the creation of a embedding text data further used for indexing it into a vector database using the specified configuration. It supports multiple embedding providers including OpenAI, Bedrock, and HuggingFace.



Parameters to be set:
+++++++++++++++


### General:


* **Embedding Method**: Choose the embedding method from HuggingFace, OpenAI, or Bedrock.
* **Chunk Size**: Define the size of text chunks for processing large inputs (default: 1024).
* **Chunk Overlap**: Set the overlap size between consecutive chunks (default: 100).
* **Content Column**: Select the column that contains the text content (default: `content`).
* **File Name Column**: Select the column that contains file names (default: `fileName`).
* **Page Number Column**: Select the column that contains page numbers (default: `pageNumber`).
* **Base64 Image Column**: Select the column that contains Base64 encoded images (default: `base64Image`).
* **User Query**: Provide a user query string for search or processing.
* **Directory Path Column**: Set the column name for directory paths (default: `directoryPath`).


### Service-Specific Configurations:


#### OpenAI:


* **API Key**: Provide your OpenAI API key.
* **Embedding Model**: Specify the OpenAI embedding model.
* **Max Retries**: Set the maximum number of retries for API calls (default: 6).
* **Embedding Context Length**: Define the context length for embeddings (default: 8191).


#### Bedrock:


* **Service Name**: Specify the Bedrock service name.
* **Region Name**: Provide the AWS region name.
* **AWS Access Key ID**: Provide your AWS Access Key ID.
* **AWS Secret Access Key**: Provide your AWS Secret Access Key.
* **Embedding Model**: Specify the Bedrock embedding model.


#### HuggingFace:


* **Model Name**: Specify the HuggingFace embedding model (default: `all-MiniLM-L6-v2`).


