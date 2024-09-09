Sklearn Logistic Regression
=========== 

Logistic Regression is a linear model for classification and implementation can fit binary, One-vs-Rest, or multinomial logistic regression with optional , or Elastic-Net regularization.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnLogisticRegression

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - targetCol
        - Target Column
        - The label column for model fitting
      * - featureCols
        - Feature Columns
        - Feature columns of type - all numeric, boolean and vector
      * - penalty
        - Penalty
        - The norm used in the penalization.
      * - dual
        - Dual
        - Dual or primal formulation.
      * - tol
        - Tol
        - Tolerance for stopping criteria.
      * - C
        - C
        - Inverse of regularization strength; must be a positive float.
      * - fit_intercept
        - Fitintercept
        - Specifies if a constant (a.k.a. bias or intercept) should be added to the decision function.
      * - intercept_scaling
        - InterceptScaling
        - Useful only when the solver 'liblinear' is used and fit_intercept is set to True.
      * - class_weight
        - ClassWeight
        - Weights associated with classes in the form {class_label: weight}.
      * - random_state
        - RandomState
        - The seed of the pseudo random number generator to use when shuffling the data.
      * - solver
        - Solver
        - Algorithm to use in the optimization problem.
      * - max_iter
        - Maxiter
        - Maximum number of iterations taken for the solvers to converge.
      * - multi_class
        - MultiClass
        - If the option chosen is 'ovr', then a binary problem is fit for each label. For 'multinomial' the loss minimised is the multinomial loss fit across the entire probability distribution.
      * - verbose
        - Verbose
        - For the liblinear and lbfgs solvers set verbose to any positive number for verbosity.
      * - warm_start
        - WarmStart
        - When set to True, reuse the solution of the previous call to fit as initialization.
      * - path
        - Save Confusion Matrix Path
        - Save Confusion Matrix
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


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html


