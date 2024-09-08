Split
=========== 

This node splits the incoming DataFrame into 2. It takes in the fraction to use in splitting the data. For example, if the fraction is .7, it would split the data into 2 DataFrames, one containing 70% of the rows(passed from lower edge id to next node) and the other containing the remaining 30%(passed from higher edge id to next node).

Input
--------------
It takes in a DataFrame as input

Output
--------------
The input DataFrame is split into 2 DataFrames and output

Type
--------- 

transform

Class
--------- 

fire.nodes.ml.NodeSplit

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - fraction1
        - Fraction 1
        - Fraction to be used for Splitting the DataFrame into two. The first DataFrame would go to the lower edge output. The other would go to the higher edge output.


Details
-------


This node splits the incoming DataFrame into 2. It takes in the fraction to use in splitting the data.

For example, if the fraction is .7, it would split the data into 2 DataFrames, one containing 70% of the rows(passed from lower edge id to next node) and the other containing the remaining 30%(passed from higher edge id to next node).

The split node can be used for splitting the DataFrame for training and test datasets used in Machine Learning.


