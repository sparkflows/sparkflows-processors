H2O Score
=========== 

Scores the data using the H2O model

Type
--------- 

ml-predict

Class
--------- 

fire.nodes.h2o.NodeH2OScore

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - isTestData
        - is Test Data
        - To enable the test metrics.
      * - labelCol
        - Label Column
        - The label column for model Transformation.
      * - withContribution
        - Compute Shapley Values
        - Compute Shapley Values and it supported for Regression and Binomial Classification problem.
      * - path
        - Path
        - Path to save the Shapley contributions for test dataset.
      * - modelType
        - Model Type
        - Select the type of the model.
      * - confusionMatrix
        - Confusion Matrix
        - 
      * - output_confusion_matrix_chart
        - Output Confusion Matrix Chart
        - Whether to display Confusion Matrix Chart.
      * - cmChartTitle
        - Confusion Matrix Chart Title
        - Title name to display in Confusion Matrix Chart
      * - cmChartDescription
        - Confusion Matrix Chart Description
        - Description to display in Confusion Matrix Chart
      * - confusionMatrixTargetLegend
        - Confusion Matrix Target Legend
        - Legend name to display for Target in Confusion Matrix
      * - confusionMatrixPredictedLabelLegend
        - Confusion Matrix PredictedLabel Legend
        - Legend name to display for Predicted Label in Confusion Matrix
      * - Description
        - Confusion Matrix Description
        - 
      * - confusionMatrixRowDescription
        - Confusion Matrix Outcome description
        - Add the business details of the outcome of the confusion matrix rows
      * - ROC Curve
        - ROC Curve
        - 
      * - output_roc_chart
        - Output ROC Curve
        - Whether to display confusion matrix chart.
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
      * - predictionOverTime
        - Prediction Over Time
        - 
      * - model_uuid
        - Model UUID
        - Enter the model uuid
      * - enablePredictionOverTimeMetrics
        - Enable Prediction Over Time Metrics
        - enable
      * - modelCategory
        - Model Category
        - Select the category


Details
===============
H2O Score Node
---------------


This node scores a new dataset using an existing H2O model. It takes a trained H2O model and an input DataFrame as input and generates predictions.


Examples
===============
H2O Score Node Example
---------------


Scenario:


Let's say you have trained an H2O model to predict customer churn. You can use the H2O Score node to apply this model to a new dataset of customer data and generate churn predictions.


Configuration:


1. **H2O Model:** Select the trained H2O model to use for scoring from model load node

2. **Output Storage Level:** Choose the storage level for the output DataFrame.


Output:


The node will output a new DataFrame containing the original input data along with the predicted values.
