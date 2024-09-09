N Gram Transformer
=========== 

Converts the input array of strings into an array of n-grams. Null values in the input array are ignored. It returns an array of n-grams where each n-gram is represented by a space-separated string of words.When the input is empty, an empty array is returned. When the input array length is less than n (number of elements per n-gram), no n-grams are returned

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
It adds a new column consisting of a sequence of nn-grams where each nn-gram is represented by a space-delimited string of nn consecutive words, to the incoming DataFrame

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeNGramTransformer

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
        - Contains sequence of strings
      * - inputColStringArrCol
        - List of Words
        - Sequence of words
      * - outputCol
        - Output Column
        - Consist of a sequence of n-grams where each n-gram is represented by a space-delimited string of n consecutive words
      * - numberOfGrams
        - Number of Grams
        - Sequence of 'string array' for integer 'Number of Grams'


Details
-------


 N-Gram Transformer Node Details
+++++++++++++++

This node converts the input string into an array of n-grams. Null values in the input array are ignored. It returns an array of n-grams where each n-gram is represented by a space-separated string of words. When the input is empty, an empty array is returned. When the input array length is less than n (number of elements per n-gram), no n-grams are returned"

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the input schema that contains the features to be converted.
*  LIST OF WORDS : Set a name of the field in the output schema that contains the tokenized values.
*  OUTPUT COLUMN : Set a name of the field in the output schema that contains the transformed features.
*  NUMBER OF GRAMS : Minimum n-gram length, greater than or equal to 1. Default is 2.


Examples
-------


 N-Gram Transformer Node Example
+++++++++++++++

Assume that we have the following DataFrame with columns id and message:

 id |       message     |
----|-------------------|
 0  | this is a spam    |
 1  |i am going to work |
 2  |this is not a spam |

 Applying the <b>N-Gram Transformer</b> node with <b>message</b> as the input column, <b>n-grams</b> with  value of 3, <b>tokenText</b> and <b>ngramText</b> as the output column, we should get the following:

 id |       message     |        tokenText        |               ngramText                 |
----|-------------------|-------------------------|-----------------------------------------|
 0  | this is a spam    |(this, is, a, spam)      | (this is a, is a spam)                  |
 1  |i am going to work |(i, am, going, to, work)	| (i am going, am going to, going to work)|
 2  |this is not a spam |(this, is, not, a, spam)	| (this is not, is not a, not a spam)     |
