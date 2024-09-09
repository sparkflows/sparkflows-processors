IDF
=========== 

Compute the Inverse Document Frequency (IDF) given a collection of documents.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output DataFrame contains a new column of type vector, It takes feature vectors (generally created from HashingTF) as input and scales each column. Intuitively, it down-weights columns which appear frequently in a corpus.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeIDF

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
        - Input Column Name
      * - outputCol
        - Output Column
        - Output column name
      * - minDocFreq
        - MinDocFreq
        - The minimum of documents in which a term should appear.


Details
-------


 IDF Node Details
+++++++++++++++

The IDF (Inverse Document Frequency) Node is a feature vectorization method widely used in text mining to reflect the importance of a term to a document in the corpus. IDF is a measure of how common any particular word or gram is in the given corpus that you are searching. It is an estimate of how rare that word is and thus its likely importance. So if a query contains an uncommon word, documents containing that rare word should be judged to be more important.
                                                                        
Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the vector field in the input schema that contains the features to build the model from.
*  OUTPUT COLUMN : A name for the output vector column.
*  MINDOCFREQ : The minimum number of documents in which a term should appear. Default: 0 


Examples
-------


 IDF Node Example
+++++++++++++++

Assume that we have a DataFrame with the column <b>strText<b>:

        strText      | 
---------------------|
 Sparkflows is cool  |
 Learn Sparkflows    |
 Sparkflows rocks!   |
 
Creating a feature vectors from the <b>strText<b> column, and applying the IDF node we get the below output column <b>vecIDF</b>

                              vecIDF                                     | 
------------------------------------------------------------------------ |
(1000,[209,372,990,995],[0.6931471805599453,0.0,0.0,0.6931471805599453]) |
(1000,[372,967,990],[0.0,0.6931471805599453,0.0])                        |
(1000,[372,962,990],[0.0,0.6931471805599453,0.0])                        |
