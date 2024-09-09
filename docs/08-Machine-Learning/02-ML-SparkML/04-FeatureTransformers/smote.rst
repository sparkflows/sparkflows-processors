SMOTE
=========== 

Implementation of SMOTE - Synthetic Minority Over-sampling Technique.

Input
--------------
This type of node takes in a DataFrame and transforms it to another DataFrame

Output
--------------
Output DataFrame

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeSMOTE

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - labelCol
        - Label Column
        - Label Column.
      * - featureCol
        - Feature Column
        - Feature Column with vector type.
      * - bucketLength
        - BucketLength
        - Bucket Length for LSH - The length of each hash bucket, a larger bucket lowers the false negative rate.


Details
-------


 SMOTE Node Details
+++++++++++++++

Synthetic Minority Oversampling Technique (SMOTE) is a statistical technique for increasing the number of cases in your dataset in a balanced way. 
The component works by generating new instances from existing minority cases that you supply as input. This implementation of SMOTE does not change the number of majority cases.

Synthetic examples are generated in the following way:

- Take the difference between the feature vector (sample) under consideration and its nearest neighbour (Using Locality Sensitive Hashing (LSH) model)
- Multiply this difference by a random number between 0 and 1, and add it to the sample
For discrete attributes, the synthetic example randomly picks either the sample or the neighbour, and copies that value.

By forcing the decision region of the minority class to become more general, SMOTE reduces overfitting.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  LABEL COLUMN : Select the field in the input schema that contains the label.
*  FEATURE COLUMN : Select the field in the input schema that contains the feature vector.
*  BUCKETLENGTH : Set the length of each hash bucket, a larger bucket lowers the false negative rate. Defaults to 100.


Examples
-------


 SMOTE Node Example
+++++++++++++++

Assume a dataset that consists of transactions made by credit cards. This dataset has <b>492</b> fraud transactions out of <b>284,807</b> transactions. 
That makes it highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

 Before OverSampling, counts of label '1': [492]
 Before OverSampling, counts of label '0': [284315] 

 After running the dataset through the <b>SMOTE</b> node we can expect the below results:

 After SMOTE OverSampling, counts of label '1': 284315
 After SMOTE OverSampling, counts of label '0': 284315

 The SMOTE node has oversampled the minority instances and made it equal to majority class. Both categories have equal amount of records. More specifically, the minority class has been increased to the total number of majority class.
 
