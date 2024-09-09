Stop Words Remover
=========== 

Filters out stop words from input. Null values from input array are preserved unless adding null to stopWords explicitly.

Output
--------------
It adds a new column containing the sequence of strings from the input column but with the stop words removed, to the incoming DataFrame.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeStopWordsRemover

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
        - Column containing the array text from which the stop words have to be removed
      * - outputCol
        - Output Column
        - Contains array of text by dropping list of stop words
      * - caseSensitive
        - Case Sensitive
        - Case Sensitive
      * - stopWords
        - Comma Separated List of Custom Stop Words. If not provided, the default list of stop words would be used.
        - Custom List of Stop Words


Details
-------


 Stop Words Remover Node Details
+++++++++++++++

Stop words are words which should be excluded from the input, typically because the words appear frequently and don’t carry as much meaning.

The Stop Words Remover node takes as input a sequence of strings (e.g. the output of a Tokenizer) and drops all the stop words from the input sequences. 

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the array column type from where we will remove the stop words.
*  OUTPUT COLUMN : The name of the output column.
*  CASE SENSITIVE : Specifies Whether to do a case sensitive comparison over the stop words. (Default = False)
*  COMMA SEPARATED LIST OF CUSTOM STOP WORDS : Optional, specify comma separated stop words. Note that the default stopwords original list can be found from "Glasgow Information Retrieval Group" http://ir.dcs.gla.ac.uk/resources/linguistic_utils/stop_words

    


Examples
-------


 Stop Words Remover Node Example
+++++++++++++++

Assume that we have the following DataFrame with columns id and raw:

 id | raw
----|----------
 0  | [I, saw, the, red, balloon]
 1  | [Mary, had, a, little, lamb]
 
Applying the <b>StopWordsRemover</b> node with <b>raw</b> as the input column and <b>filtered</b> as the output column, we should get the following:

 id | raw                         | filtered
----|-----------------------------|--------------------
 0  | [I, saw, the, red, balloon]  |  [saw, red, balloon]
 1  | [Mary, had, a, little, lamb]|[Mary, little, lamb]
