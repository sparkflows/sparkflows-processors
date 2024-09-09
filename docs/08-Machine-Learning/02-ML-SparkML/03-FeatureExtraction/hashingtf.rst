Hashing TF
=========== 

Maps a sequence of terms to term frequencies using the hashing trick.

Input
--------------
It takes in a DataFrame as input and transforms it to another DataFrame

Output
--------------
A new column is added to the input DataFrame containing hashing of the bag of words into a feature vector

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeHashingTF

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
        - Contains sets of terms. In text processing, a 'set of terms' might be a bag of words
      * - outputCol
        - Output Column
        - Output column name


Details
-------


 Hashing TF Node Details
+++++++++++++++

The Hashing TF Node maps a sequence of terms to their term frequencies using the hashing trick. Currently we use Austin Appleby’s MurmurHash 3 algorithm (MurmurHash3_x86_32) to calculate the hash code value for the term object.

Hashing TF converts documents to vectors of fixed size. The default feature dimension is 262,144. The terms are mapped to indices using a Hash Function. The term frequencies are computed with respect to the mapped indices.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the input token column from the incoming schema. 
*  OUTPUT COLUMN : Set a name of the output transformed column.


Examples
-------


 Hashing TF Node Example
+++++++++++++++

Consider the below <b>Hashing TF</b> vector output for the <b>tokenizer</b> column.

|-----------------------------------------------------------------------------|
|       Title         |       tokenizer         |           hashTF            |
|-----------------------------------------------------------------------------|
| Learning Sparkflows | (learning, sparkflows)  |   (1000,[72,990],[1.0,1.0]) |
