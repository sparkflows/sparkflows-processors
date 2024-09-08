SageMaker Linear Learner Regressor
=========== 

Node runs the SageMaker-provided Linear Regressor algorithm. The SageMakerEstimator is an org.apache.spark.ml.Estimator that trains a model on Amazon SageMaker.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sagemaker.NodeLinearLearnerRegressor

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - roleArn
        - Role Arn
        - Role arn to use sagemaker
      * - trainingInstanceType
        - Training Instance Type
        - InstanceType for training
      * - trainingInstanceCount
        - Training Instance Count
        - Number of Instance for training
      * - endpointInstanceType
        - Endpoint InstanceType
        - InstanceType for Endpoint
      * - endpointInitialInstanceCount
        - Endpoint Initial Instance Count
        - Number of Instance for Endpoint




