Hugging Face Natural Language Inference
=========== 

Natural Language Inference using models hosted in Hugging Face repository.

Input
--------------
It takes in a DataFrame as input with two sentences seperated by a period

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.gai.NodeHFNaturalLanguageInference

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - column_name
        - Column for Question Natural Language Inference
        - Column for Question Natural Language Inference.
      * - preloaded_model
        - Model to be used for Question Natural Language Inference
        - Infers if the sentences are entailment(hypothesis is true), contraction(hypothesis is false) or neutral(no relationship between hypothesis and the premise).
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.




