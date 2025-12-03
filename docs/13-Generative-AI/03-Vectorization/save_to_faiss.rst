Save Faiss DB
=========== 

Save Vector Embeddings to faiss db

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSaveToFaissDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - fileNameCol
        - File Name Column
        - Column name for file names.
      * - pageNumberCol
        - Page Number Column
        - Column name for page numbers.
      * - contentCol
        - Content Column
        - Column name for text content.
      * - directoryPathCol
        - Directory Path Column
        - Column name for directory paths.
      * - embeddingsCol
        - Embeddings Column
        - Column name for embeddings.
      * - base64ImageCol
        - Base64 Image Column
        - Column name for Base64 encoded images.
      * - faissIndexName
        - FAISS Index Name
        - Name of the FAISS index.
      * - faissIndexDir
        - FAISS Index Directory Path
        - Directory path for the FAISS index.
      * - dimension
        - Dimension
        - Dimension for embeddings.


Details
===============
Save Faiss DB Node Details
---------------

The Save Faiss DB node stores vector embeddings and associated metadata from a DataFrame into a FAISS vector database, enabling efficient similarity search and retrieval. It is designed for PySpark-based workflows, making it suitable for integrating vector-based storage into data pipelines. The node allows specification of columns for text content, embeddings, and metadata, which are saved to a FAISS index for later querying.



General:
+++++++++++++++



File Name Column: Specifies the DataFrame column containing file names associated with the content. Default is 'fileName'. This is optional and used for metadata tracking.
+++++++++++++++



Page Number Column: Specifies the DataFrame column containing page numbers for multi-page documents. Default is 'pageNumber'. This is optional and relevant for documents like PDFs.
+++++++++++++++



Content Column: Specifies the DataFrame column containing the text content to be stored. Default is 'content'. This is required to associate text with the embeddings.
+++++++++++++++



Directory Path Column: Specifies the DataFrame column containing directory paths for the source files. Default is 'directoryPath'. This is optional and used for metadata tracking.
+++++++++++++++



Embeddings Column: Specifies the DataFrame column containing the embeddings (vector representations) of the text content. Default is 'embeddings'. This is required for storage in the FAISS database.
+++++++++++++++



Base64 Image Column: Specifies the DataFrame column containing base64-encoded images associated with the content. Default is 'base64Image'. This is optional and used for storing image-related metadata.
+++++++++++++++



FAISS Index Name: Specifies the name of the FAISS index where the embeddings will be stored. Default is 'faiss_index'. This is required to identify the index.
+++++++++++++++



FAISS Index Directory Path: Specifies the directory path (local or distributed filesystem) where the FAISS index will be saved. This is required to store the index.
+++++++++++++++



Dimension: Specifies the dimensionality of the embeddings. Default is 0, which must be overridden to match the embedding model (e.g., 1536 for text-embedding-ada-002, 1024 for multilingual-e5-large). This is required for proper index creation.
+++++++++++++++



Output:
+++++++++++++++

The node saves the embeddings, content, and optional metadata (file names, page numbers, directory paths, base64 images) to the specified FAISS index in the designated directory. It does not produce a DataFrame output but confirms the successful storage of data in the FAISS vector database, ready for similarity search and retrieval.


Examples
===============
Example: Save Faiss DB Node
---------------



Input:
+++++++++++++++

A DataFrame contains the following data:


* fileName: ["report.pdf", "study.docx"]
* pageNumber: [1, 1]
* content: ["Climate change impacts ecosystems...", "AI advancements in 2025..."]
* directoryPath: ["/data/docs/", "/data/docs/"]
* embeddings: [[0.12, 0.45, ...], [0.23, 0.67, ...]] (1024-dimensional vectors)
* base64Image: ["iVBORw0KGgoAAAANSUhEUg...", null]


The Save Faiss DB node is configured as follows:


* File Name Column: fileName
* Page Number Column: pageNumber
* Content Column: content
* Directory Path Column: directoryPath
* Embeddings Column: embeddings
* Base64 Image Column: base64Image
* FAISS Index Name: faiss_index
* FAISS Index Directory Path: /data/faiss_indices/
* Dimension: 1024


Output:
+++++++++++++++


The node stores the embeddings and associated data in the FAISS vector database under the index named 'faiss_index' in the directory '/data/faiss_indices/'. The stored data includes:


* Vectors from the embeddings column (1024-dimensional).
* Text from the content column.
* Metadata from the fileName, pageNumber, directoryPath, and base64Image columns.


The FAISS index is now ready for similarity search queries.



Explanation:
+++++++++++++++


* The node processes the DataFrame, extracting the embeddings and content columns to store in the FAISS index named 'faiss_index'.
* The fileName, pageNumber, directoryPath, and base64Image columns are stored as metadata, providing additional context for each vector (e.g., fileName: "report.pdf", base64Image: base64-encoded image for the first row, null for the second).
* The Dimension is set to 1024 to match the embedding model (e.g., multilingual-e5-large).
* The FAISS Index Directory Path ('/data/faiss_indices/') specifies where the index is saved.
* If optional columns like Base64 Image Column or Directory Path Column were not provided, they would not be included as metadata in the FAISS index.
* The node ensures the FAISS index is created or updated with the provided data, making it available for efficient similarity searches.
