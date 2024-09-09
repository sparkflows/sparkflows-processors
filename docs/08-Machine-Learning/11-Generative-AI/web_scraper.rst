Web Scraper
=========== 

Scrapes Webpages

Input
--------------
It takes in a DataFrame as input

Type
--------- 

dataset

Class
--------- 

fire.nodes.gai.NodeWebScraper

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - site
        - Webpage to Crawl
        - Enter website url
      * - output_file
        - Path
        - Select a path to save Scraped data
      * - output_file_format
        - Output File Format
        - Output File Format.
      * - scrape_recursively
        - Scrape Recursively
        - when True, will perform a recursive search of this PageElement's children. Otherwise, only the direct children will be considered.
      * - limit
        - Limit
        - Stop looking after finding this many results when scrape recursively is True.




