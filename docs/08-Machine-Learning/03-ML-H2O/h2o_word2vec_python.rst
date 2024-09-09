H2O Word to Vec
=========== 

The Word2vec algorithm takes a text corpus as an input and produces the word vectors as output.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.h2o.NodeH2OWord2vec

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
        - Input column name.
      * - vecSize
        - Vec Size
        - Set size of word vectors.
      * - windowSize
        - Window Size
        - Set max skip length between words.
      * - sentSampleRate
        - Sent Sample Rate
        - Set the threshold for the occurrence of words. Those words that appear with higher frequency in the training data will be randomly down-sampled. An ideal range for this option 0, 1e-5.
      * - normModel
        - Normalization Model
        - Use Hierarchical Softmax.
      * - epochs
        - Epochs
        - Number of training iterations to run.
      * - minWordFreq
        - Min Word Frequency
        - SThis will discard words that appear less than <int> times.
      * - initLearningRate
        - Init Learning Rate
        - Set the starting learning rate.
      * - wordModel
        - Word Model
        - Uhe word model to use (SkipGram or CBOW).
      * - maxRuntimeSecs
        - Max Runtime Secs
        - his argument specifies the maximum time that the AutoML process will run for. If both max_runtime_secs and max_models are specified, then the AutoML run will stop as soon as it hits either of these limits. If neither max_runtime_secs nor max_models are specified, then max_runtime_secs defaults to 3600 seconds (1 hour).
      * - columnsToCategorical
        - Columns to Categorical
        - Columns to be Categorical encoded


Details
-------


The Word2vec algorithm takes a text corpus as an input and produces the word vectors as output. The algorithm first creates a vocabulary from the training text data and then learns vector representations of the words.

More details are available at : http://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science/word2vec.html#


