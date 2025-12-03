Hugging Face Grammatical Correctness
=========== 

Grammatical Correctness using models hosted in Hugging Face repository.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.gai.NodeHFSentimentAnalysis

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - column_name
        - Column to check for Grammatical Correctness
        - Column to check for Grammatical Correctness.
      * - preloaded_model
        - Model to be used for checking Grammatical Correctness
        - Checks for grammatical correctness.
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.




