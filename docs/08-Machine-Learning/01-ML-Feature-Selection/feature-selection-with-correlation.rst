Feature Selection With Correlation
=========== 



Output
--------------
Pass the input DataFrame to output and in table format correlation value between target and feature columns displayed.

Type
--------- 

transform

Class
--------- 

fire.nodes.featureselection.FeatureSelectionWithCorrelation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - targetCol
        - TargetCol
        - 
      * - featureCols
        - Feature Columns
        - 


Details
-------


 Feature Selection With Correlation Node Details
+++++++++++++++

This node enables us to discover the possible correlation which can exist between a defined target column and the feature column's.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TARGETCOL : Select the target variable for which we want to explore the existence of a relationship.
*  FEATURE COLUMNS : 

  - Available : A list of numeric feature columns derived from the input dataframe schema.
  - Selected : A list of columns for whom the node will compute correlational values against the TARGETCOL.


Examples
-------


 Feature Selection With Correlation Node Example
+++++++++++++++

For a given dataframe having the below housing schema:
price  | bathrms | stories| bedrooms|
Double | Double  | Double | Double  |
-------------------------------------

We can select the Target Columns as <b>price</b> and explore the correlation which exists between the target column and the feature columns of <b>bathrms</b>, <b>stories</b> and <b>bedrooms</b>.

This will yield two output sections:
- A Correlation table showing the correlation value between the target column price and the feature columns &
- Output of the input dataframe in tabular format
