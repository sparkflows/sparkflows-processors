String Indexer Advanced Transform
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

ml-predict

Class
--------- 

fire.nodes.ml.NodeStringIndexerAdvancedTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description


Details
-------


 String Indexer Transform Node Details
+++++++++++++++

The String Indexer Transform Node is used to encode a string column of labels to a column of label indices. It takes in an input DataFrame and transforms it to another DataFrame. It also takes in a fit model as input, which is typically the output of a previous String Indexer Estimator Node.
The transformed DataFrame contains a new column with the encoded label indices.

Input Parameters
```````````````

FIT MODEL : The output of a previous String Indexer Estimator Node, which contains the information about the encoding of the labels.


Examples
-------


 String Indexer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'gender' containing string values. We use a String Indexer Estimator Node to encode the string values to label indices, creating a fit model. Then, we use the String Indexer Transform Node to encode the 'gender' column using the fit model.

Input DataFrame:

id gender
1 male
2 female
3 male
4 female

Output

id gender gender_encoded
1 male 1
2 female 0
3 male 1
4 female 0
In this example, the input column is 'gender' and the output column is 'gender_encoded'. The fit model is created using the String Indexer Estimator Node. The String Indexer Transform Node uses this fit model to encode the 'gender' column, creating a new column 'gender_encoded' with the encoded label indices.
