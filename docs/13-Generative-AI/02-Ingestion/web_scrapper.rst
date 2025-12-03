Web Scraper
=========== 

Scrapes Webpages

Input
--------------
It takes in a DataFrame as input

Type
--------- 

transform

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
      * - siteCol
        - Webpage to Crawl
        - Select website url
      * - scrape_recursively
        - Scrape Recursively
        - when True, will perform a recursive search of this PageElement's children. Otherwise, only the direct children will be considered.
      * - limit
        - Depth
        - Stop looking after finding this many results when scrape recursively is True.


Details
===============
Web Scraper Node Details
---------------

The Web Scraper node is designed to extract content from webpages, starting from a specified URL. It collects text from a wide range of HTML elements, cleans it to remove unwanted characters (e.g., newlines, tabs) and boilerplate phrases (e.g., "top of page," "bottom of page"), and can optionally crawl linked pages within the same domain up to a specified limit. The node outputs a DataFrame containing the cleaned text and corresponding URLs for each scraped page.




Webpage to Crawl:Specifies the starting URL for the web scraping process. This is the initial webpage from which content is extracted and, if recursive scraping is enabled, the starting point for discovering linked pages.
+++++++++++++++


Required: Yes



Scrape Recursively:Controls whether the node follows links on the webpage to scrape additional pages within the same domain.
+++++++++++++++


Options:

`true`: Recursively crawls linked pages within the same domain, up to the specified depth.

`false`: Scrapes only the specified webpage without following links.



Default: true



Depth:Defines the maximum number of pages to scrape when Scrape Recursively is set to true. The node stops once this limit is reached.
+++++++++++++++


Default: 5

Example: 3



Output:The node outputs a DataFrame with the following columns:
+++++++++++++++


text: The cleaned text content extracted from the webpage, free of newlines, tabs, excessive spaces, and boilerplate phrases (e.g., "top of page," "bottom of page").

metadata: The URL of the scraped webpage.Each row represents a single scraped page, with up to Depth pages included in the output.


