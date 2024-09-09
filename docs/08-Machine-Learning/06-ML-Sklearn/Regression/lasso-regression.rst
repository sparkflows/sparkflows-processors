SkLearn Lasso Regression
=========== 

In Lasso Regression, Linear Model trained with L1 prior as regularizer.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sklearn.NodeSklearnLassoRegression

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
        - Constant that multiplies the L1 term. Defaults to 1.0. Alpha = 0 is equivalent to an ordinary least square, solved by the LinearRegression object.
      * - fit_intercept
        - Fit Intercept
        - Whether to calculate the intercept for this model. If set to false, no intercept will be used in calculations.
      * - normalize
        - Normalize
        - This parameter is ignored when `fit_intercept` is set to False. If True, the regressors X will be normalized before regression.
      * - precompute
        - Precompute
        - Whether to use a precomputed Gram matrix to speed up calculations.
      * - max_iter
        - Max Iterations
        - The maximum number of iterations.
      * - tol
        - Tolerance
        - The tolerance for the optimization: if the updates are smaller than `tol`, the optimization code checks the dual gap for optimality and continues until it is smaller than `tol`.
      * - warm_start
        - Warm Start
        - When set to True, reuse the solution of the previous call to fit as initialization, otherwise, just erase the previous solution.
      * - positive
        - Positive
        - When set to True, forces the coefficients to be positive.
      * - random_state
        - Random State
        - The seed of the pseudo random number generator that selects a random feature to update.
      * - selection
        - Selection
        - If set to ‘random’, a random coefficient is updated every iteration rather than looping over features sequentially by default. This (setting to ‘random’) often leads to significantly faster convergence especially when tol is higher than 1e-4.


Details
-------


More details are available at : https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html


