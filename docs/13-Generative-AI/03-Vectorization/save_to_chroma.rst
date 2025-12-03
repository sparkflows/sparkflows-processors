Save Chroma DB
=========== 

Save Vector Embeddings to Chroma DB

Input
--------------
It takes in a DataFrame as input

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSaveToChromaDB

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - text
        - Content Column
        - Column name for text content.
      * - embeddings
        - Embeddings Column
        - Column name for embeddings.
      * - collection
        - Collection Name (case sensitive)
        - Name of ChromaDB Collection to add embeddings to. Creates collection, if collection doesn't exist.




