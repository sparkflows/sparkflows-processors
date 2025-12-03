Read Pinecone DB
=========== 

Read Vector Embeddings from Pinecone db

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeReadFromPineconeDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - topK
        - Top K
        - Number of top results to retrieve (default: 3).
      * - pineconeConnection
        - Select Pinecone Connection
        - Select Pinecone Connection
      * - pineconeIndexName
        - Pinecone Index Name
        - Name of the Pinecone index.
      * - indexNameSpace
        - Index Namespace
        - Namespace for organizing the Pinecone index.
      * - userQueryCol
        - User Query Column
        - Column name for user query (default: 'userQuery').
      * - queryEmbeddingCol
        - Query Embedding Column
        - Column name for query embeddings (default: 'embeddings').


Details
===============
Read Pinecone DB Node Details
---------------

The Read Pinecone DB node retrieves vector embeddings from a Pinecone vector database based on a user query or query embeddings provided in a DataFrame. It performs a similarity search to find the most relevant documents and returns the results as a DataFrame with columns for the user query and corresponding content. This node is designed for PySpark-based workflows, enabling efficient retrieval of vector-based data for similarity search applications.



General:
+++++++++++++++



Top K: Specifies the number of top results to retrieve from the Pinecone index based on similarity. Default is 3. Must be a positive integer.
+++++++++++++++



Select Pinecone Connection: Specifies the connection details for the Pinecone API (e.g., API key, environment). This is required to authenticate and access the Pinecone service.
+++++++++++++++



Pinecone Index Name: Specifies the name of the Pinecone index to query. This is required and must match an existing index in the Pinecone database.
+++++++++++++++



Index Namespace: Specifies the namespace within the Pinecone index to query. This is optional; if provided, it narrows the search to the specified namespace.
+++++++++++++++



User Query Column: Specifies the DataFrame column containing the user query (text input for similarity search). Default is 'userQuery'. This is required if querying with text input.
+++++++++++++++



Query Embedding Column: Specifies the DataFrame column containing pre-computed query embeddings (vector representations). Default is 'embeddings'. This is required if querying with embeddings instead of text.
+++++++++++++++



Output:
+++++++++++++++

The node outputs a DataFrame with the following columns:


* userquery: The original query from the User Query Column or derived from the query embeddings.
* content: The content of the top matching documents retrieved from the Pinecone index, based on similarity to the query.


Examples
===============
Example: Read Pinecone DB Node
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* userQuery: ["What is climate change?", "AI advancements in 2025"]
* embeddings: [[0.12, 0.45, ...], [0.23, 0.67, ...]] (1024-dimensional vectors)


The Read Pinecone DB node is configured as follows:


* Top K: 3
* Select Pinecone Connection: Configured with a valid Pinecone API key and environment
* Pinecone Index Name: document-index
* Index Namespace: document-namespace
* User Query Column: userQuery
* Query Embedding Column: embeddings


Output:
+++++++++++++++


The node queries the Pinecone database and produces a DataFrame with the following structure:


::

    userquery                    | content
    -----------------------------|--------------------------------------
    What is climate change?      | Climate change refers to long-term shifts in weather patterns...
    AI advancements in 2025      | Recent AI advancements include improved neural networks...



Explanation:
+++++++++++++++


* The node processes the DataFrame, using the userQuery and embeddings columns to perform a similarity search in the Pinecone index 'document-index' under the 'document-namespace' namespace.
* The Top K setting of 3 ensures that up to three matching documents are retrieved for each query based on similarity to the provided embeddings.
* The User Query Column ('userQuery') provides the text query, which is included in the output DataFrame for reference.
* The Query Embedding Column ('embeddings') supplies the vector representations used for the similarity search in Pinecone.
* The content column contains the text of the most relevant documents retrieved from the Pinecone index.
* If Index Namespace was left empty, the search would encompass the entire index without namespace filtering.
* If only text queries were provided without embeddings, the node would rely on the Pinecone service to generate embeddings internally (if supported by the connection).
