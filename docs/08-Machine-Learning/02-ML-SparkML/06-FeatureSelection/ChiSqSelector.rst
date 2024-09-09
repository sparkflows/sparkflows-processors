ChiSq Selector
=========== 

Chi-Squared feature selection, which selects categorical features to use for predicting a categorical label.

Type
--------- 

ml-transformer

Class
--------- 

fire.nodes.ml.NodeChiSqSelector

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - featuresCol
        - Features Column 
        - The features column name
      * - outputCol
        - Output Column
        - The output column name
      * - labelCol
        - Label Column
        - The label column name
      * - numTopFeatures
        - NumTopFeatures
        - Number of features that selector will select (ordered by statistic value descending).
      * - percentile
        - Percentile
        - Percentile of features that selector will select, ordered by statistics value descending. Only applicable when selectorType is percentile
      * - fpr
        - FPR
        - The highest p-value for features to be kept. Only applicable when selectorType is fpr
      * - fdr
        - FDR
        - The upper bound of the expected false discovery rate. Only applicable when selectorType is fdr
      * - fwe
        - FWE
        - The upper bound of the expected family-wise error rate. Only applicable when selectorType is fwe
      * - selectorType
        - Selector Type
        - The selector type of the ChisqSelector.


Details
-------


ChiSqSelector stands for Chi-Squared feature selection. It operates on labeled data with categorical features. ChiSqSelector uses the Chi-Squared test of independence to decide which features to choose.

More details are available at : http://spark.apache.org/docs/latest/ml-features.html#chisqselector


Examples
-------


The below example is available at :  http://spark.apache.org/docs/latest/ml-features.html#chisqselector
+++++++++++++++

import org.apache.spark.ml.feature.ChiSqSelector
import org.apache.spark.ml.linalg.Vectors

val data = Seq(
  (7, Vectors.dense(0.0, 0.0, 18.0, 1.0), 1.0),
  (8, Vectors.dense(0.0, 1.0, 12.0, 0.0), 0.0),
  (9, Vectors.dense(1.0, 0.0, 15.0, 0.1), 0.0)
)

val df = spark.createDataset(data).toDF("id", "features", "clicked")

val selector = new ChiSqSelector()
  .setNumTopFeatures(1)
  .setFeaturesCol("features")
  .setLabelCol("clicked")
  .setOutputCol("selectedFeatures")

val result = selector.fit(df).transform(df)
result.show()
