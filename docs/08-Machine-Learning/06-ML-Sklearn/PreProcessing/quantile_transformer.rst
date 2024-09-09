Sklearn Quantile Fit Transform
=========== 

Transform features using quantiles information.

Type
--------- 

transform

Class
--------- 

fire.nodes.sklearn.preprocessing.NodeQuantileTransformerFitTransform

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - n_estimators
        - N-Estimators
        - 
      * - output_distribution
        - Output Distribution
        - 
      * - ignore_implicit_zeros
        - Ignore Implicit Zeros
        - 
      * - subsample
        - Subsample


Details
-------


  h2: Sklearn Quantile Fit Transform Node Details

  The Sklearn Quantile Fit Transform Node is used to transform features using quantiles information. It transform the features using quantiles information. It takes in the input data and applies the transformation to the features. The input data can be in the form of a numpy array or a pandas DataFrame.
  It also takes 4 parameters: n_estimators, output_distribution, ignore_implicit_zeros and subsample.

  n_estimators: The number of quantiles to compute.
  output_distribution: The type of output distribution. It can be 'uniform' or 'normal'
  ignore_implicit_zeros: it is a boolean parameter. If it is set to true, it will ignore the implicit zeros when computing the quantile statistics.
  subsample: The maximum number of samples to include in the subsample to compute the quantiles.

  h4:Input Parameters

  N-ESTIMATORS : The number of quantiles to compute.
  OUTPUT DISTRIBUTION : The type of output distribution. It can be 'uniform' or 'normal'
  IGNORE IMPLICIT ZEROS : if it is set to true, it will ignore the implicit zeros when computing the quantile statistics.
  SUBSAMPLE : The maximum number of samples to include in the subsample to compute the quantiles.

  


Examples
-------


  h2: Sklearn Quantile Fit Transform Node Example

  Consider the below <b>Sklearn Quantile Fit Transform</b> output for the <b>features</b> column

  id features transformed_features
  0 [1.0, 2.0, 3.0, 4.0] [0.25, 0.5, 0.75, 1.0]
1 [-1.0, -2.0, -3.0, -4.0] [-0.25, -0.5, -0.75, -1.0]
In this example, the input column is features and the output column is transformed_features. The n_estimators parameter is set to 1000, output_distribution parameter is set to "uniform", ignore_implicit_zeros is set to false and subsample parameter is set to 100000. The transformer applies quantile transformation to the features column.
