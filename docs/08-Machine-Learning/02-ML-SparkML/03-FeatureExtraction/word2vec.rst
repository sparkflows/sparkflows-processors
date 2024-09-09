Word2 Vec
=========== 

Transforms vectors of words into vectors of numeric codes for the purpose of further processing by NLP or machine learning algorithms.

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
A new column containing feature vector is added to the incoming DataFrame

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeWord2Vec

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCol
        - Input Column
        - Contains sequences of words
      * - inputColStringArrCol
        - Text Array Column
        - The text array column which is produced
      * - outputCol
        - Output Column
        - Output column name
      * - vectorSize
        - Vector Size
        - Vector Size
      * - minCount
        - Min Count
        - Min Count
      * - numPartitions
        - Num Partitions
        - Number of partitions for sentences of words
      * - windowSize
        - Window Size
        - The window size (context words from [-window, window])
      * - maxSentenceLength
        - Max Sentence Length
        - Sets the maximum length (in words) of each sentence in the input data. Any sentence longer than this threshold will be divided into chunks of up to maxSentenceLength


Details
-------


 Word2Vec Node Details
+++++++++++++++

The Word2Vec Node is an Estimator which takes sequences of words representing documents and trains a Word2VecModel. The model maps each word to a unique fixed-size vector. The Word2VecModel transforms each document into a vector using the average of all words in the document; this vector can then be used for as features for prediction, document similarity calculations, etc.

The word2vec algorithm uses a model to learn word associations from a large corpus of text. Once trained, such a model can detect synonymous words or suggest additional words for a partial sentence.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : The name of the field in the input schema that contains the features to build the model from.
*  TEXT ARRAY COLUMN : Set a name for the output transformed array column. 
*  OUTPUT COLUMN : Set a name for the output vector column. 
*  VECTOR SIZE : The dimension of the code that you want to transform from words. Defaults to 3.
*  MIN COUNT : The minimum number of times a token must appear to be included in the word2vec model's vocabulary.
*  NUM PARTITIONS : Number of partitions for sentences of words. 
*  WINDOW SIZE  : Hyperparameter used in training process. Defaults to 5.  
*  MAX SENTENCE LENGTH : Sets the maximum length (in words) of each sentence in the input data. 


Examples
-------


 Word2Vec Node Example
+++++++++++++++

Consider the below <b>Word2Vec</b> output's for the input string <b>Title</b> column.

*  Title : 'Learning Sparkflows'
*  textarr : (Learning, Sparkflows)
*  Word2Vec : [-0.12955643981695175,0.0201990008354187,0.13060205057263374]
