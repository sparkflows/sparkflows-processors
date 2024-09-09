Tokenizer
=========== 

A tokenizer that converts the input string to lowercase and then splits it by white spaces.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It adds a new column containing the results of tokenization of the input column, to the incoming DataFrame.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeTokenizer

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
        - Column containing text (such as sentence)
      * - outputCol
        - Output Column
        - Output column name


Details
-------


 Tokenizer Node Details
+++++++++++++++

Tokenization is essentially splitting a phrase, sentence, paragraph, or an entire text document into smaller units, such as individual words or terms. Each of these smaller units are called tokens. The Tokenizer node accepts an string input and breaks the string into an array of tokens.
                                                                        
Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the required string column for whom tokenization has to be done . 
*  OUTPUT COLUMN : The name of the output tokenized column.


Examples
-------


 Tokenizer Node Example
+++++++++++++++

Assume that we have a DataFrame with the column <b>strText<b>:

          strText             | 
----------------------------- |
 Sparkflows is cool to learn. |
 
 If we set Tokenizer's <b>INPUT COLUMN</b> to strText and <b>OUTPUT COLUMN</b> to tokens, after transformation we should get the following DataFrame:

                  tokens                       | 
---------------------------------------------- |
WrappedArray(sparkflows, is, cool, to, learn.) |
