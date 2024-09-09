Sklearn Ridge Regression
=========== 

Ridge Regression, solves a regression model where the loss function is the linear least squares function and regularization is given by the l2-norm.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnRidgeRegression

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
      * - alpha
        - Alpha
        - Constant that multiplies the L2 term, regularization strength.
      * - fitintercept
        - Fit Intercept
        - Whether to calculate the intercept for this model.
      * - normalize
        - Normalize
        - This parameter is ignored when `fit_intercept` is set to False. If True, the regressors X will be normalized before regression by subtracting the mean and dividing by the l2-norm.
      * - maxiter
        - Max Iterations
        - Maximum number of iterations for conjugate gradient solver.
      * - tol
        - Tolerance
        - Precision of the solution.
      * - solver
        - Solver
        - Solver to use in the computational routines.
      * - randomstate
        - Random State
        - The seed of the pseudo random number generator to use when shuffling the data for the solver.'


Details
-------


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html


