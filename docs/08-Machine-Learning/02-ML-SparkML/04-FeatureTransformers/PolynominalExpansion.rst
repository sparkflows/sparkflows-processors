Polynominal Expansion
=========== 

Perform feature expansion in a polynomial space

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
The output DataFrame contains a new column of type vector, Expanding your features into a polynomial space, which is formulated by an n-degree combination of original dimensions.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodePolynominalExpansion

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
        - The input column name
      * - outputCol
        - Output Column
        - The output column name
      * - degree
        - Degree
        - The polynomial degree to expand, which should be >= 1. A value of 1 means no expansion.


Details
-------


 Polynominal Expansion Node Details
+++++++++++++++

The Polynomial expansion Node helps in the process of expanding your features into a polynomial space, which is formulated by an n-degree combination of original dimensions.

For example, if a dataset had one input feature X, then a polynomial feature would be the addition of a new feature (column) where values were calculated by squaring the values in X, e.g. X^2. This process can be repeated for each input variable in the dataset, creating a transformed version of each.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the required vector column from the list of input schema fields. 
*  OUTPUT COLUMN : Set a name for the output column.
*  DEGREE : The polynomial degree to expand, which should be greater than or equal to 1.  A value of 1 means no  expansion. Default : 2.


Examples
-------


 Polynominal Expansion Node Example
+++++++++++++++

Consider the below dataset which contains a vector field <b>features</b>

|features  |
|:--------:|
|[2.0,1.0] |
|[3.0,-1.0]|

On applying the <b>Polynominal Expansion Node</b> to the input  column of <b>features</b> with a <b>degree</b> of 3, we get the below output dataframe with the output vector column of <b>polyFeatures</b>.

|features  |          polyFeatures                    |
|:--------:|:----------------------------------------:|
|[2.0,1.0] |[2.0,4.0,8.0,1.0,2.0,4.0,1.0,2.0,1.0]     |
|[3.0,-1.0]|[3.0,9.0,27.0,-1.0,-3.0,-9.0,1.0,3.0,-1.0]|
