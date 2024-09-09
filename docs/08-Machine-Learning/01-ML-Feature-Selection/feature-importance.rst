Feature Selection With Importance
=========== 



Output
--------------
Pass the input DataFrame to output and in table format feature importance is displayed.

Type
--------- 

transform

Class
--------- 

fire.nodes.featureselection.NodeFeatureSelectionWithImportance

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
        - Target column to be used when selecting the features
      * - featureCols
        - Feature Columns
        - The list of columns for which to calculate the feature importance
      * - mlType
        - MLType
        - target column type, Regression or Classification


Details
-------


 Feature Selection With Importance Node Details
+++++++++++++++

This node used Random Forest which is a very powerful model both for regression and classification. It can give its own interpretation of feature importance as well, which can be plotted and used for selecting the most informative set of features.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TARGETCOL : Select the target variable for which we want to explore the existence of a relationship.
*  FEATURE COLUMNS : 

  - Available : A list of numeric feature columns derived from the input dataframe schema.
  - Selected : A list of columns for whom the node will compute correlational values against the TARGETCOL.

*  MLTYPE : Select the type of machine learning model for the input data, choose between <b>Regression</b> or <b>Classification</b> model.


Examples
-------


 Feature Selection With Importance Node Example
+++++++++++++++

For a given dataframe having the below housing schema:
price  | bathrms | stories| bedrooms|
Double | Double  | Double | Double  |
-------------------------------------

We can select the Target Columns as <b>price</b> and explore the correlation which exists between the target column and the feature columns of <b>bathrms</b>, <b>stories</b> and <b>bedrooms</b> for a <b>Regression</b> model.

This will yield two output sections:
- A Feature Importance table showing the correlation percentage between the target column  and the feature columns &
- Output of the input dataframe in tabular format
