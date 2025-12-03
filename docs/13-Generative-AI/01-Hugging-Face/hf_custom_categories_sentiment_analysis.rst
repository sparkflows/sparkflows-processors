Hugging Face Custom Category Sentiment Analysis
=========== 

Sentiment Analysis with custom categories using models hosted in Hugging Face repository.

Input
--------------
It takes in a DataFrame as input

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.gai.NodeHFCustomCategoriesSentimentAnalysis

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
      * - category_list
        - Category lists
        - Comma seperated categories to classify. Can be space & cosmos, scientific discovery, microbiology, robots, archeology, travel, cooking, dancing etc
      * - preloaded_model
        - Model to be used for Sentiment analysis
        - Computes the sentiment using the model chosen.
      * - preloaded_model_path
        - Path
        - Pre-loaded models parent directory.
      * - custom_model
        - Custom model name
        - Model name to pull model from Hugging Face repo.




