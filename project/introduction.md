## Directory Structure

Our Scripts Project uses python language and uses scrapy as majoy framework. 

For purpose to crawler all news article, need two scripts(List,articles).

- List script: scrape the site's home pages to save all links on the database as 'Cache' table row.
- Articles script: scrape the detailed articles by url stored on 'Cache' table row. 

The project structure looks something like this:


```
.
├── main.py
├── scrapy.cfg
├── setup.py
├── cwpoliticl/
|   ├── scraped_websites.py
|   └── something.md
```

An overview of what each of these does:



| File                     |     Description                                                 |
|-------------------------:|----------------------------------------------------:|
| main.py                  |        only used for develop, you can run it locally                   |
| scrapy.cfg               | Scrapyd searches for configuration files in the following locations, and parses them |
| Setup.py                 | Automatically created by: scrapyd-deploy |
| scraped_websites.py      | Stored all scraped websites data                   |






