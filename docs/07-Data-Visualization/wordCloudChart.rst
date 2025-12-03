Word Cloud Chart
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeWorldCloudChart

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - title
        - Title
        - 
      * - description
        - Description
        - 
      * - descriptionColor
        - Description Color
        - 
      * - topWordCount
        - Top Word Count
        - Word count to display
      * - chartColors
        - Chart Colors
        - 
      * - isWordCloud
        - Word cloud
        - Render graph as Word Cloud if user select true and Sentence cloud if false


Details
-------
Purpose:


This node creates a word cloud to visualize the frequency of words in a text document or a column of text data. It's useful for identifying the most common words and themes in a text corpus.


Configuration:


Title: Set the title for the chart.

Description: Add a description for the chart.

Top Word Count: Specify the maximum number of words to display in the word cloud.

Chart Colors: Customize the color palette for the words.

Word Column: Select the column containing the text data.

Output:


The node will generate a word cloud where the size of each word is proportional to its frequency in the text. The colors of the words can be customized to enhance visual appeal.


Use Cases:


Text Analysis: Identify the most frequent words and themes in text documents.

Sentiment Analysis: Analyze the sentiment of text data by visualizing the frequency of positive and negative words.

Topic Modeling: Discover underlying topics in a text corpus.


Examples
-------
Example:


Let's say you have a dataset of customer reviews. You can use the Word Cloud node to visualize the most frequently used words in the reviews.


Configuration:


Word Column: ReviewText


Output:


The word cloud will display the most frequent words in the customer reviews. The size of each word will indicate its frequency.
