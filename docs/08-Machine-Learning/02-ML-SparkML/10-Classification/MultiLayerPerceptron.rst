MultiLayer Perceptron
=========== 

It supports creation of full connected neural network.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ml.NodeMultilayerPerceptron

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
        - The prediction column created during model scoring.
      * - splitRatio
        - Split Ratio
        - Split Ratio
      * - layers
        - Layers - comma separated list of integers
        - The integer array specifying the number of activation units in each layer
      * - maxIter
        - Max number of iterations
        - Number of iterations to train the Neural network
      * - blockSize
        - Block Size
        - Block size
      * - seed
        - Seed
        - The initial seed to initialise the neural network.
      * - tol
        - Tol
        - 
      * - solver
        - Solver
        - solver
      * - stepSize
        - Step Size
        - Step size
      * - confusionMatrix
        - Confusion Matrix
        - 
      * - output_confusion_matrix_chart
        - Output Confusion Matrix Chart
        - whether to display confusion matrix chart.
      * - cm_chart_title
        - Confusion Matrix Chart Title
        - Title name to display in Confusion Matrix Chart
      * - cm_chart_description
        - Confusion Matrix Chart Description
        - Description to display in Confusion Matrix CHart
      * - confusionMatrixTargetLegend
        - Confusion Matrix Target Legend
        - Legend name to display for Target in Confusion Matrix
      * - confusionMatrixPredictedLabelLegend
        - Confusion Matrix PredictedLabel Legend
        - Legend name to display for Predicted Label in Confusion Matrix
      * - confusionMatrixCountLegend
        - Confusion Matrix Count Legend
        - Legend name to display for Count in Confusion Matrix
      * - Description
        - Confusion Matrix Description
        - 
      * - confusionMatrixRowDescription
        - Confusion Matrix Outcome description
        - One can provide the business details of the outcome of the confusion matrix rows
      * - ROC Curve
        - ROC Curve
        - 
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
===============
Multilayer perceptron classifier (MLPC) is a classifier based on the feedforward artificial neural network. 

MLPC consists of multiple layers of nodes. Each layer is fully connected to the next layer in the network. Nodes in the input layer represent the input data.


Examples
===============
Below example is available at : https://spark.apache.org/docs/latest/ml-classification-regression.html#multilayer-perceptron-classifier


import org.apache.spark.ml.classification.MultilayerPerceptronClassifier

import org.apache.spark.ml.evaluation.MulticlassClassificationEvaluator


// Load the data stored in LIBSVM format as a DataFrame.

val data = spark.read.format("libsvm")

  .load("data/mllib/sample_multiclass_classification_data.txt")


// Split the data into train and test

val splits = data.randomSplit(Array(0.6, 0.4), seed = 1234L)

val train = splits(0)

val test = splits(1)


// specify layers for the neural network:

// input layer of size 4 (features), two intermediate of size 5 and 4

// and output of size 3 (classes)

val layers = Array[Int](4, 5, 4, 3)


// create the trainer and set its parameters

val trainer = new MultilayerPerceptronClassifier()

  .setLayers(layers)

  .setBlockSize(128)

  .setSeed(1234L)

  .setMaxIter(100)


// train the model

val model = trainer.fit(train)


// compute accuracy on the test set

val result = model.transform(test)

val predictionAndLabels = result.select("prediction", "label")

val evaluator = new MulticlassClassificationEvaluator()

  .setMetricName("accuracy")


println(s"Test set accuracy = ${evaluator.evaluate(predictionAndLabels)}")
