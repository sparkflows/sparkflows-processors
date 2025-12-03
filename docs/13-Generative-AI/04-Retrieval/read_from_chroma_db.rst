Read Chroma DB
===========

Read Vector Embeddings from Chroma DB Collection gives user query

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeReadFromChromaDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - userQuery
        - Query Column
        - Column name for queries
      * - userQueryEmbeddings
        - Query Embeddings Column
        - Column name for query embeddings.
      * - collection
        - Collection Name (case sensitive)
        - Name of ChromaDB Collection to query from.
      * - topK
        - Top K
        - Return the K most similar results to the query




