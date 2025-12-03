Read Faiss DB
===========

Read Vector Embeddings, from faiss db

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeReadFromFaissDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - faissIndexDir
        - Path Of FAISS Index Directory
        - Enter FAISS Index Directory path.
      * - topK
        - Top K
        - Consider the top k(3) probable words at each step during text generation.
      * - faissIndexName
        - Name Of FAISS Index
        - Enter FAISS Index Name.


Details
-------
Read Faiss DB Node Details
+++++++++++++++

The Read Faiss DB node retrieves vector embeddings from a FAISS vector database based on a user query or query embeddings provided in a DataFrame. It performs a similarity search to find the most relevant documents and returns the results as a DataFrame with columns for the user query and corresponding content. This node is designed for PySpark-based workflows, enabling efficient retrieval of vector-based data for similarity search applications.



General:
+++++++++++++++


Path Of FAISS Index Directory: Specifies the directory path (local or distributed filesystem) where the FAISS index is stored. This is required and must point to a valid directory containing the FAISS index.


Top K: Specifies the number of top results to retrieve from the FAISS index based on similarity. Default is 3. Must be a positive integer.


Name Of FAISS Index: Specifies the name of the FAISS index to query. This is required and must match an existing index in the specified directory.



Output:
+++++++++++++++

The node outputs a DataFrame with the following columns:


* userquery: The original query from the input DataFrame or derived from the query embeddings.
* content: The content of the top matching documents retrieved from the FAISS index, based on similarity to the query.


Examples
-------
Example: Read Faiss DB Node
+++++++++++++++



Input:
+++++++++++++++

A DataFrame contains the following data:


* userQuery: ["What is climate change?", "AI advancements in 2025"]
* embeddings: [[0.12, 0.45, ...], [0.23, 0.67, ...]] (1024-dimensional vectors)


The Read Faiss DB node is configured as follows:


* Path Of FAISS Index Directory: /data/faiss_indices/
* Top K: 3
* Name Of FAISS Index: faiss_index


Output:
+++++++++++++++


The node queries the FAISS database and produces a DataFrame with the following structure:


::

    userquery                    | content
    -----------------------------|--------------------------------------
    What is climate change?      | Climate change refers to long-term shifts in weather patterns...
    AI advancements in 2025      | Recent AI advancements include improved neural networks...



Explanation:
+++++++++++++++


* The node processes the DataFrame, using the userQuery and embeddings columns to perform a similarity search in the FAISS index named 'faiss_index' located in the '/data/faiss_indices/' directory.
* The Top K setting of 3 ensures that up to three matching documents are retrieved for each query based on similarity to the provided embeddings.
* The userquery column in the output DataFrame contains the original text queries from the input DataFrame for reference.
* The content column contains the text of the most relevant documents retrieved from the FAISS index.
* The Path Of FAISS Index Directory and Name Of FAISS Index settings ensure the node queries the correct index in the specified location.
* If the input DataFrame only provided text queries without embeddings, the node would rely on the FAISS service to generate embeddings internally (if supported by the configuration).
