Vector Indexer Transform
=========== 

Vector Indexer indexes categorical features inside of a Vector. It decides which features are categorical and converts them to category indices. The decision is based on the number of distinct values of a feature.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It indexes categorical features in datasets of Vectors and stores the result into a new column of the DataFrame.

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ml.NodeVectorIndexerTransform

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


 Vector Indexer Transform Node Details
+++++++++++++++

The Vector Indexer Transform Node is used to index categorical features inside of a Vector. It takes in an input DataFrame and transforms it to another DataFrame. The decision of which features are categorical is based on the number of distinct values of a feature. The transformed DataFrame contains a new column with the indexed categorical features.

Input Parameters
```````````````

DataFrame : The input DataFrame which contains the features to be indexed.


Examples
-------


 Vector Indexer Transform Node Example
+++++++++++++++

Consider the following example, where we have a DataFrame with a column 'features' containing Vector values. We use the Vector Indexer Transform Node to index the categorical features in the 'features' column.

Input DataFrame:

id features
1 [1.0,2.0,3.0,"dog"]
2 [4.0,5.0,"cat",6.0]
3 [7.0,8.0,"dog",9.0]
4 [10.0,"cat",11.0,12.0]

Output

id features indexed_features
1 [1.0,2.0,3.0,"dog"] [1.0,2.0,3.0,0]
2 [4.0,5.0,"cat",6.0] [4.0,5.0,1,6.0]
3 [7.0,8.0,"dog",9.0] [7.0,8.0,0,9.0]
4 [10.0,"cat",11.0,12.0] [10.0,1,11.0,12.0]
In this example, the input column is 'features' and the output column is 'indexed_features'. The Vector Indexer Transform Node indexes the categorical features in the 'features' column, creating a new column 'indexed_features' with the indexed categorical features.
