String Indexer
=========== 

StringIndexer encodes a string column of labels to a column of label indices

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It adds a new column containing the encoding of the string column of labels to a column of label indices, to the incoming DataFrame.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeStringIndexer

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - handleInvalid
        - Handle Invalid
        - Invalid entries to be skipped or thrown error
      * - inputCols
        - Input Columns
        - Input columns for encoding
      * - outputCols
        - Output Columns
        - Output columns
      * - stringOrderType
        - String Order Type
        - Param for how to order labels of string column


Details
-------


 String Indexer Node Details
+++++++++++++++

The String Indexer node encodes a string column of labels to a column of label indices. The indices are in [0, numLabels).

By default, this is ordered by label frequencies so the most frequent label gets index 0. The ordering behavior is controlled by setting <b>STRING ORDER TYPE</b>. Its default value is ‘frequencyDesc’. In case of equal frequency when under frequencyDesc/Asc, the strings are further sorted alphabetically

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  HANDLE INVALID : Specifies how to handle invalid data (unseen or NULL values) in features and label column of string type. Options are 'skip' (filter out rows with invalid data), or error (throw an error).
*  VARIABLES : Allows multiple string columns to be selected for conversion.
*  Input Columns : Select the column which needs to be converted.
*  Output Columns : The name of the output converted column.
*  STRING ORDER TYPE : Specifies how to order labels of string column. (default = "frequencyDesc")

- Supported options are:
    "frequencyDesc": descending order by label frequency (most frequent label assigned 0)
    "frequencyAsc": ascending order by label frequency (least frequent label assigned 0)
    "alphabetDesc": descending alphabetical order
    "alphabetAsc": ascending alphabetical order 


Examples
-------


 String Indexer Node Example
+++++++++++++++

Assume that we have the following DataFrame with columns id and category:

 id | category
----|----------
 0  | a
 1  | b
 2  | c
 3  | a
 4  | a
 5  | c
category is a string column with three labels: "a", "b", and "c". Applying <b>StringIndexer</b> with <b>category</b> as the input column and <b>categoryIndex</b> as the output column, we should get the following:

 id | category | categoryIndex
----|----------|---------------
 0  | a        | 0.0
 1  | b        | 2.0
 2  | c        | 1.0
 3  | a        | 0.0
 4  | a        | 0.0
 5  | c        | 1.0
"a" gets index 0 because it is the most frequent, followed by "c" with index 1 and "b" with index 2.
