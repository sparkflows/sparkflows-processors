Count Vectorizer
=========== 

Extracts the vocabulary from a given collection of documents and generates a vector of token counts for each document.

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
It adds a new column to the incoming DataFrame containing the vector of token counts in the input column, to generate the output DataFrame

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeCountVectorizer

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
        - Input column name
      * - outputCol
        - Output Column
        - Output column name
      * - vocabularySize
        - Vocabulary Size
        - Max size of the vocabulary.
      * - minDF
        - Min DF
        - Specifies the minimum number of different documents a term must appear in to be included in the vocabulary
      * - maxDF
        - Max DF
        - Specifies the maximum number of different documents a term could appear in to be included in the vocabulary
      * - minTF
        - Min TF
        - Filter to ignore rare words in a document
      * - binary
        - Binary
        - Binary toggle to control the output vector values.


Details
-------


 Count Vectorizer Node Details
+++++++++++++++

Machines cannot understand characters and words. So when dealing with text data we need to represent it in numbers to be understood by the machine. The Count Vectorizer Node is used to convert text to numerical data.

When an a-priori dictionary is not available, CountVectorizer can be used as an Estimator to extract the vocabulary, and generates a CountVectorizerModel. The model produces sparse representations for the documents over the vocabulary, which can then be passed to other algorithms like LDA.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the token column from the input schema . 
*  OUTPUT COLUMN : The name of the output field that contains the transformed features.
*  VOCABULARY SIZE : The maximum size of the vocabulary. If this value is smaller than the total number of different terms, the vocabulary will contain the top terms ordered by term frequency across the corpus. Default is 3.
*  MIN DF : Specifies the minimum nonnegative number of different documents a term must appear in to be included in the vocabulary. Default is 1.
*  MAX DF : Specifies the maximum number of different documents a term could appear in to be included in the vocabulary. A term that appears more than the threshold will be ignored. Default (2^63) - 1').
*  MIN TF : Filter to ignore rare words in a document. For each document, terms with frequency (or count) less than the given threshold are ignored. Default is 1.
*  BINARY : By setting 'binary = True', the node no more takes into consideration the frequency of the term/word. If it occurs it's set to 1 otherwise 0. By default, binary is set to False.


Examples
-------


 Count Vectorizer Node Example
+++++++++++++++

Assume that we have the following DataFrame with columns id and texts:

 id |         texts
----|------------------------------
 0  | Array("a", "b", "c")
 1  | Array("a", "b", "b", "c", "a")
each row in texts is a document of type Array[String]. Invoking the <b>Count Vectorizer</b> node produces the output column <b>vector</b> as shown below:

 id |             texts               |     vector
----|---------------------------------|--------------------------
 0  | Array("a", "b", "c")            | (3,[0,1,2],[1.0,1.0,1.0])
 1  | Array("a", "b", "b", "c", "a")  | (3,[0,1,2],[2.0,2.0,1.0])
Each vector represents the token counts of the document over the vocabulary.
