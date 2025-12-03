Paragraph Splitter
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeParagraphSplitter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - filePath
        - Path
        - Path for text file to be parsed
      * - outputCol
        - Output Column
        - Name for output column
      * - dropTopRows
        - Drop First N rows
        - Drop Top N Rows
      * - dropBottomRows
        - Drop Last N rows
        - Drop Bottom N Rows


Details
-------
Paragraph Splitter Node
---------------



Overview:
+++++++++++++++


The Paragraph Splitter node splits text data into paragraphs based on specified delimiters. It's particularly useful for processing text data like articles, blog posts, or emails.



Input:
+++++++++++++++


Input Column: The column containing the text data to be split.

Paragraph Separator: The delimiter used to separate paragraphs (e.g., "\\n\\n").

Drop First N Rows: The number of rows to skip from the beginning.

Drop Last N Rows: The number of rows to skip from the end.



Output:
+++++++++++++++


The node outputs a new column containing the split paragraphs.


Examples
-------
Example:


Let's assume we have a column named "text" containing the following text:


This is the first paragraph.


This is the second paragraph.


This is the third paragraph.

Configure the Node:


Input Column: text

Paragraph Separator: "\\n\\n"

Node Execution:


The node will split the text into three paragraphs and create a new column containing the split paragraphs.
