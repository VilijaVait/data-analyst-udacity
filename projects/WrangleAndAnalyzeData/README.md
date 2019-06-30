Udacity - Wrangle and Analyze Data - Data Analyst Nanodegree Project
--------------------------------------------------------------------

Objective is to gather, assess, clean and subsequently briefly analyse
the tweet data obtained from WeRateDogs twitter channel. The analysis is
not meant to be definitive and scientific, especially when it comes to
dog ratings actaully given, or dog stages defined within tweets, because
the nature of the chanel is not to be ultimate judges.

Data Sources
------------

The following three data sources were used:

1.  The WeRateDogs Twitter archive, provided as a file on hand, which
    was to be downloaded manually.

2.  The tweet image predictions, i.e., what breed of dog (or other
    object, animal, etc.) is present in each tweet according to a neural
    network. This file was hosted on Udacity's and was downloaded
    programmatically.

3.  Each tweet's retweet count and favorite ("like") count at minimum,
    and any additional data was to be downloaded using the tweet IDs in
    the WeRateDogs Twitter archive, by querying the Twitter API for each
    tweet's JSON data using Python's Tweepy library, and stored line by
    line (each line in JSON format) to new file called tweet\_json.txt
    file.

Getting Started
---------------

Data originally provided: `twitter-archive-enhanced.csv` and `twitter\_image\_class.csv` 

Twitter API - all queried JSON data: `tweet\_json.txt` 

Twitter API select dataframe: `twitter\_status\_dogs.csv` 

Data files after cleaning: `twitter\_archive\_master.csv` and `twitter\_archive\_master\_class.csv`

Working Jupyter Notebooks: 

> Gathering: 'wrangle\_project\_notebook\_gather\_nokeys.ipynb' 

> Cleaning: 'wrangle\_project\_notebook\_clean.ipynb' 

> Analysis: 'wrangle\_project\_notebook\_visual.ipynb' 

Final reports: 

> Wrangling report: 'wrangle\_report.ipynb' and 'wrangle\_report.html' 

> Data analysis report: 'act\_report.ipynb' and 'act\_report.html'

Prerequisites
-------------

Jupyter Notebooks, original data provided, Twitter API access (or use `tweet\_json.txt` instead)
