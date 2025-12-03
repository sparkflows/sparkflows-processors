Sklearn TF-IDF Vectorizer
===========

Applies scikit-learn's TfidfVectorizer to a text column. Converts text documents into TF-IDF feature vectors and stores them as an ARRAY column in the Spark DataFrame.

Input
--------------
Takes a DataFrame with at least one text column.

Output
--------------
Adds a new column containing TF-IDF vectors as ARRAY and passes the DataFrame to downstream nodes.

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeTFIDFVectorizerFitTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - columnToVectorize
        - Text Column to Vectorize
        - Name of the text column on which TF-IDF should be computed.
      * - outputCol
        - Output Column Name
        - Name of the output column that will store TF-IDF vectors as ARRAY. If left empty, defaults to 'tfidf_<columnToVectorize>'.
      * - max_df
        - Max Document Frequency (max_df)
        - Ignore terms that appear in more than this proportion of documents. For example, 0.9 drops terms appearing in more than 90% of documents.
      * - min_df
        - Min Document Frequency (min_df)
        - Ignore terms that appear in fewer than this number of documents. For example, 2 keeps only terms that appear in at least 2 documents.




