Hugging Face Question Natural Language Inference
=========== 

Question Natural Language Inference using models hosted in Hugging Face repository.

Input
--------------
It takes in a DataFrame as input with multiple sentences with first sentence being a question ending with a question mark.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.gai.NodeHFQuestionNaturalLanguageInference

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - column_name
        - Column to analyse sentiment
        - Column to analyse sentiment.
      * - preloaded_model
        - Model to be used for Natural Language Inference
        - Infers if the sentences are entailment(hypothesis is true), contraction(hypothesis is false) or neutral(no relationship between hypothesis and the premise).
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.




