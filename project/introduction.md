## Directory Structure

Our Scripts Project uses python language and uses scrapy as majoy framework. 

For purpose to crawler all news article, need two scripts(List,articles).

- List script: scrape the site's home pages to save all links on the database as 'Cache' table row.
- Articles script: scrape the detailed articles by url stored on 'Cache' table row. 

The project structure looks something like this:


