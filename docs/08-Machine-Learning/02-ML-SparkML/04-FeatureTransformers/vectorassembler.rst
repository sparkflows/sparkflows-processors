Vector Assembler
=========== 

Merges multiple columns into a vector column.

Input
--------------
It takes in a DataFrame and transforms it to another DataFrame

Output
--------------
It adds a new column to the incoming DataFrame. The new column contains the values of the input columns concatenated into a vector in the specified order.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeVectorAssembler

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Columns
        - Input column of type - all numeric, boolean and vector
      * - outputCol
        - Output Column
        - Output column name
      * - handleInvalid
        - HandleInvalid
        - How to handle invalid data (NULL values). Options are 'skip' (filter out rows with invalid data), 'error' (throw an error), or 'keep' (return relevant number of NaN in the output).




Examples
-------


 h2: VectorAssembler Node Example
+++++++++++++++

Assume that we have a DataFrame with the columns id, hour, mobile, userFeatures, and clicked:

 id | hour | mobile | userFeatures     | clicked
----|------|--------|------------------|---------
 0  | 18   | 1.0    | [0.0, 10.0, 0.5] | 1.0

 If we set VectorAssembler's <b>input Selected columns</b> to hour, mobile, and userFeatures and <b>output column</b> to features, after transformation we should get the following DataFrame:

 id | hour | mobile | userFeatures     | clicked | features
----|------|--------|------------------|---------|-----------------------------
 0  | 18   | 1.0    | [0.0, 10.0, 0.5] | 1.0     | [18.0, 1.0, 0.0, 10.0, 0.5]
