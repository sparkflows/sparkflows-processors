Regex Tokenizer
=========== 

This node creates a new DataFrame by the process of taking text (such as a sentence) and breaking it into individual terms (usually words) based on regular expression

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRegexTokenizer

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCol
        - Column
        - input column for tokenizing
      * - outputCol
        - Tokenized Column
        - New output column after tokenization
      * - pattern
        - Pattern
        - The regex pattern used to match delimiters
      * - gaps
        - Gaps
        - Indicates whether the regex splits on gaps


Details
-------
Regex Tokenizer Node
---------------



Overview:
+++++++++++++++


The Regex Tokenizer node splits text data into tokens based on a regular expression pattern. This is useful for tasks like text preprocessing, natural language processing, and information extraction.



Input:
+++++++++++++++


Column: The column containing the text data to be tokenized.

Tokenized Column: The name of the new column to store the tokenized text.

Pattern: The regular expression pattern to use for tokenization.

Gaps: A flag indicating whether to include gaps (spaces) between tokens.


Output:
+++++++++++++++


The node creates a new column containing the tokenized text.


Examples
-------
Example:
---------------


Let's assume we have a column named text containing the following text:


This is a sample text.

Configure the Node:


Column: text

Tokenized Column: tokens

Pattern: \w+ (matches word characters)

Gaps: True

Node Execution:


The node will split the text into tokens based on word boundaries and create a new column tokens containing the following:


This,is,a,sample,text
