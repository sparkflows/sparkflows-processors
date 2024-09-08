SageMaker Linear Learner Binary Classifier
=========== 

Node runs the SageMaker-provided Linear Learner Binary Classifier algorithm. The SageMakerEstimator is an org.apache.spark.ml.Estimator that trains a model on Amazon SageMaker.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.sagemaker.NodeLinearLearnerBinaryClassifier

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
        - Endpoint Instance Type
        - InstanceType for Endpoint
      * - endpointInitialInstanceCount
        - Endpoint Initial Instance Count
        - Number of Instance for Endpoint




