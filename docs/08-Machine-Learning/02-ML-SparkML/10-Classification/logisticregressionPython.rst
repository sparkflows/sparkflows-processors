Logistic Regression
=========== 

Logistic regression. Currently, this class only supports binary classification.

Input
--------------
This takes in a DataFrame and performs Logistic Regression

Output
--------------
The Logistic Regression Model generated is passed along to the next nodes. The input DataFrame is also passed along to the next nodes

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeLogisticRegression

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
        - Features column of type vectorUDT for model fitting
      * - labelCol
        - Label Column
        - The label column for model fitting
      * - predictionCol
        - Prediction Column
        - The prediction column created during model scoring
      * - maxIter
        - Maximum Iterations
        - Maximum number of iterations (>= 0)
      * - fitIntercept
        - Fit Intercept
        - Whether to fit an intercept term
      * - regParam
        - Regularization Param
        - The regularization parameter
      * - standardization
        - Standardization
        - Whether to standardize the training features before fitting the model
      * - threshold
        - Threshold
        - The threshold in binary classification prediction
      * - tol
        - Tolerance
        - The convergence tolerance for iterative algorithms
      * - elasticNetParam
        - ElasticNet Param
        - The ElasticNet mixing parameter. For alpha = 0, the penalty is an L2 penalty. For alpha = 1, it is an L1 penalty
      * - weightCol
        - Weight Column
        - If the 'weight column' is not specified, all instances are treated equally with a weight 1.0
      * - aggregationDepth
        - Aggregation Depth
        - Param for suggested depth for treeAggregate (>= 2)
      * - family
        - Family
        - Param for the name of family which is a description of the label distribution to be used in the model
      * - gridSearch
        - Grid Search
      * - regParamGrid
        - Regularization Param Grid Search
        - Regularization Parameters for Grid Search
      * - elasticNetGrid
        - ElasticNet Param Grid Search
        - ElasticNet Parameters for Grid Search
      * - confusionMatrix
        - Confusion Matrix
      * - output_confusion_matrix_chart
        - Output Confusion Matrix Chart
        - whether to display confusion matrix chart.
      * - cm_chart_title
        - Confusion Matrix Chart Title
        - Title name to display in Confusion Matrix Chart
      * - cm_chart_description
        - Confusion Matrix Chart Description
        -  Description to display in Confusion Matrix CHart
      * - confusionMatrixTargetLegend
        - Confusion Matrix Target Legend
        - Legend name to display for Target in Confusion Matrix
      * - confusionMatrixPredictedLabelLegend
        - Confusion Matrix PredictedLabel Legend
        - Legend name to display for Predicted Label in Confusion Matrix
      * - confusionMatrixCountLegend
        - Confusion Matrix Count Legend
        - Legend name to display for Count in Confusion Matrix
      * - confusionMatrixCountLegend
        - Confusion Matrix Count Legend
        - Legend name to display for Count in Confusion Matrix
      * - Description
        - Confusion Matrix Description
      * - confusionMatrixRowDescription
        - Confusion Matrix Outcome description
        - One can provide the business details of the outcome of the confusion matrix rows
      * - ROC Curve
        - ROC Curve
      * - output_roc_curve
        - Output ROC Curve
        - whether to display confusion matrix chart.
      * - roc_title
        - ROC Curve Chart Title
        - Title name to display in ROC Curve Chart
      * - roc_description
        - ROC Curve Chart Description
        - Add Description for ROC Curve Chart
      * - xlabel
        - X Label
        - X label
      * - ylabel
        - Y Label
        - Y Label


Details
-------


Logistic regression is a popular method to predict a categorical response. 

It is a special case of Generalized Linear models that predicts the probability of the outcomes. 
In spark.ml logistic regression can be used to predict a binary outcome by using binomial logistic regression, or it can be used to predict a multiclass outcome by using multinomial logistic regression.

More details are available at:

http://spark.apache.org/docs/latest/ml-classification-regression.html#logistic-regression


Examples
-------


The below example is available at : https://spark.apache.org/docs/2.3.0/ml-classification-regression.html#logistic-regression
+++++++++++++++


import org.apache.spark.ml.classification.LogisticRegression

// Load training data
val training = spark.read.format("libsvm").load("data/mllib/sample_libsvm_data.txt")

val lr = new LogisticRegression()
  .setMaxIter(10)
  .setRegParam(0.3)
  .setElasticNetParam(0.8)

// Fit the model
val lrModel = lr.fit(training)

// Print the coefficients and intercept for logistic regression
println(s"Coefficients: ${lrModel.coefficients} Intercept: ${lrModel.intercept}")

// We can also use the multinomial family for binary classification
val mlr = new LogisticRegression()
  .setMaxIter(10)
  .setRegParam(0.3)
  .setElasticNetParam(0.8)
  .setFamily("multinomial")

val mlrModel = mlr.fit(training)

// Print the coefficients and intercepts for logistic regression with multinomial family
println(s"Multinomial coefficients: ${mlrModel.coefficientMatrix}")
println(s"Multinomial intercepts: ${mlrModel.interceptVector}")
