Hugging Face Tone Analysis
=========== 

Tone Analysis using models hosted in Hugging Face repository.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.gai.NodeHFToneAnalysis

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
        - Model to be used for Tone analysis
        - Computes the top N tones using the model chosen.
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.




