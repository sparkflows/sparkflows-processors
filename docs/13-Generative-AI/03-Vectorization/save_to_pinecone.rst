Save to Pinecone
=========== 

This process involves storing document embeddings in a Pinecone vector database for efficient similarity search and retrieval.

Input
--------------
It may take in Dataframe as an input

Output
--------------
Save data to Vector DB

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSaveToPineconeDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - contentCol
        - Select Content Column
        - Select Content Column
      * - embeddingsCol
        - Select Embeddings Column
        - Select Embeddings Column
      * - pineconeConnection
        - Select Pinecone Connection
        - Select Pinecone Connection
      * - pineconeIndexName
        - Index Name
        - The name of the Pinecone index to create.
      * - indexNameSpace
        - Index Namespace
        - Pinecone Index Namespace
      * - dimension
        - Dimension
        - For text-embedding-ada-002 and amazon.titan-embed-text-v1, dimension is 1536; for multilingual-e5-large, dimension is 1024.
      * - metric
        - Metric
        - Type of metric used in the vector index when querying.
      * - metadataCols
        - Metadata Columns
        - Metadata Columns
      * - uniqueIdCols
        - Unique ID Columns
        - Unique ID Columns


Details
===============
Save to Pinecone Node Details
---------------

The Save to Pinecone node stores document embeddings in a Pinecone vector database, enabling efficient similarity search and retrieval. It takes a DataFrame as input, containing text content and corresponding embeddings, and saves them to a specified Pinecone index. This node is designed for PySpark-based workflows, making it ideal for integrating vector-based storage and search into data pipelines.



General:
+++++++++++++++



Select Content Column: Specifies the DataFrame column containing the text content to be stored in the Pinecone vector database. This is required to associate text with the embeddings.
+++++++++++++++



Select Embeddings Column: Specifies the DataFrame column containing the embeddings (vector representations) of the text content. This is required for storage in the vector database.
+++++++++++++++



Select Pinecone Connection: Specifies the connection details for the Pinecone API (e.g., API key, environment). This is required to authenticate and access the Pinecone service.
+++++++++++++++



Index Name: Specifies the name of the Pinecone index where the embeddings will be stored. Default is 'document-index'. If the index does not exist, it will be created.
+++++++++++++++



Index Namespace: Specifies the namespace within the Pinecone index to organize the stored embeddings. Default is 'document-namespace'. This is optional and used to group related vectors.
+++++++++++++++



Dimension: Specifies the dimensionality of the embeddings. Default is 1024 (suitable for models like multilingual-e5-large). For other models, such as text-embedding-ada-002 or amazon.titan-embed-text-v1, the dimension is typically 1536. This must match the embedding model used.
+++++++++++++++



Metric: Specifies the distance metric used for similarity search in the Pinecone index. Options are:
+++++++++++++++


* cosine: Cosine similarity metric.
* dotproduct: Dot product metric.
* euclidean: Euclidean distance metric (default).


Metadata Columns: Specifies one or more DataFrame columns to include as metadata for the stored embeddings. This is optional and allows additional context to be stored alongside the vectors.
+++++++++++++++



Unique ID Columns: Specifies one or more DataFrame columns to use as unique identifiers for the stored embeddings. This is optional; if provided, these IDs are used to reference the vectors in the Pinecone index.
+++++++++++++++



Output:
+++++++++++++++


The node saves the embeddings, content, and optional metadata to the specified Pinecone index and namespace. It does not produce a DataFrame output but confirms the successful storage of data in the Pinecone vector database, ready for similarity search and retrieval.


Examples
===============
Example: Save to Pinecone Node
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* doc_id: ["doc1", "doc2"]
* content: ["This is a report about climate change...", "A study on AI advancements..."]
* embeddings: [[0.12, 0.45, ...], [0.23, 0.67, ...]] (1024-dimensional vectors)
* category: ["Environment", "Technology"]


The Save to Pinecone node is configured as follows:


* Select Content Column: content
* Select Embeddings Column: embeddings
* Select Pinecone Connection: Configured with a valid Pinecone API key and environment
* Index Name: document-index
* Index Namespace: document-namespace
* Dimension: 1024
* Metric: cosine
* Metadata Columns: [category]
* Unique ID Columns: [doc_id]


Output:
+++++++++++++++


The node stores the embeddings in the Pinecone vector database under the 'document-index' index and 'document-namespace' namespace. The stored data includes:


* Vectors from the embeddings column (1024-dimensional).
* Corresponding text from the content column.
* Metadata from the category column (e.g., "Environment", "Technology").
* Unique IDs from the doc_id column (e.g., "doc1", "doc2").


The Pinecone index is now ready for similarity search queries using the cosine metric.



Explanation:
+++++++++++++++


* The node processes the DataFrame, extracting the content and embeddings columns to store in the Pinecone vector database.
* The doc_id column is used as unique identifiers for each vector, allowing for easy retrieval.
* The category column is stored as metadata, providing additional context for each vector (e.g., "Environment" for doc1).
* The Index Name ('document-index') and Index Namespace ('document-namespace') organize the stored vectors in the Pinecone database.
* The Dimension is set to 1024 to match the embedding model (e.g., multilingual-e5-large), and the Metric is set to cosine for similarity searches.
* If Metadata Columns or Unique ID Columns were left empty, no metadata or custom IDs would be stored, and Pinecone would generate default IDs for the vectors.
