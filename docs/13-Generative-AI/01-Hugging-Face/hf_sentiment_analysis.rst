Hugging Face Sentiment Analysis
=========== 

Sentiment Analysis using models hosted in Hugging Face repository.

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
        - Column to analyse sentiment
        - Column to analyse sentiment.
      * - preloaded_model
        - Model to be used for Sentiment analysis
        - Computes the sentiment using the model chosen.
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.
      * - explain_prediction
        - Top word affecting the sentiment per row?
        - Do you need the top word affecting the sentiment per row? Computation takes time




