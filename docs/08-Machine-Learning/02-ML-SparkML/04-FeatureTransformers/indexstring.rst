Index String
=========== 

Maps a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeIndexString

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
        - Column containing label indices
      * - outputCol
        - Output Column
        - Output column name


Details
-------


 Index String Node Details
+++++++++++++++

An Index String Node is a Transformer that maps a column of indices back to a new column of corresponding string values. The index-string mapping is either from the ML attributes of the input column, or from user-supplied labels (which take precedence over ML attributes).
A common use case is to produce indices from labels with StringIndexer, train a model with those indices and retrieve the original labels from the column of predicted indices with IndexToString.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  INPUT COLUMN : Select the column of label indices which needs to be transformed to its original category.
*  OUTPUT COLUMN : A name for the output column which will contain the original label after transformation.


Examples
-------


 Index String Node Example
+++++++++++++++

Consider the below datafrme which contains the transformed string column 'category' to indexed column 'categoryIndex'

----------------------------
| id|category|categoryIndex|
----------------------------
|  0|       a|          0.0|
|  1|       b|          2.0|
|  2|       c|          1.0|
|  3|       a|          0.0|
|  4|       a|          0.0|
|  5|       c|          1.0|
----------------------------

On applying the <b>Index String Node</b> to the input column of <b>categoryIndex</b> we get the original string column <b>originalCategory</b>.

------------------------------------
| id|categoryIndex|originalCategory|
------------------------------------
|  0|          0.0|               a|
|  1|          2.0|               b|
|  2|          1.0|               c|
|  3|          0.0|               a|
|  4|          0.0|               a|
|  5|          1.0|               c|
------------------------------------
