Vector Indexer
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

ml-estimator

Class
--------- 

fire.nodes.etl.NodeVectorIndexer

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
        - The Input column name
      * - outputCol
        - Output Column
        - Output column name
      * - maxCategories
        - Maximum Categories
        - Threshold for the number of values a categorical feature can take. If a feature is found to have > maxCategories values, then it is declared continuous. Must be >= 2


Details
-------


 Vector Indexer Node Details
+++++++++++++++

The Vector Indexer Node is used to index categorical features inside of a Vector. It converts categorical features to category indices by deciding which features are categorical based on the number of distinct values of a feature.

It takes in the common parameters inputCol, outputCol, and maxCategories. The input column should be in the format of VectorUDT. The output column will also be in the format of VectorUDT.

The inputCol is the name of the feature column to be transformed. The outputCol is the name of the new column containing the indexed features. The maxCategories parameter is a threshold for the number of values a categorical feature can take. If a feature is found to have more than maxCategories values, it is declared continuous. It must be >= 2.

Input Parameters
```````````````

INPUT COLUMN : Select the required column for which indexing has to be done.
OUTPUT COLUMN : The name of the output column after indexing.
MAX CATEGORIES : Threshold for the number of values a categorical feature can take. If a feature is found to have > maxCategories values, then it is declared continuous. Must be >= 2.


Examples
-------


 Vector Indexer Node Example
+++++++++++++++

Consider the below <b>Vector Indexer</b> output for the <b>features</b> column

id features indexed_features
0 [1.0, 2.0, 3.0, 4.0] [0.0, 1.0, 2.0, 3.0]
1 [-1.0, -2.0, -3.0, -4.0] [0.0, 1.0, 2.0, 3.0]
In this example, the input column is features and the output column is indexed_features. The vector indexer indexes the categorical features in the features column by considering them as categorical features and converting them to category indices. Here the maxCategories parameter is set to 4, so all 4 values in the feature column are considered as categorical and are indexed as 0,1,2,3.
