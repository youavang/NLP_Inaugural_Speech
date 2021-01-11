# Inaugural Speech Analysis with NLP

We used NLP techniques to analyze presidential inaugural speeches and compare them in several ways. We analyzed the past four presidents' first inaugural speeches by comparing their word cloud, total unique words, total words per speech, their overall sentiment, their sentiment throughout the speech, and defining the topic of their speech. The steps we took for this project was 1) collect data, 2) explore data, 3) clean data 4) analyze data, 5) find sentiment, and 6) topic modeling.

## Collect Data
We used BeautifulSoup to collect data from [The American Presidency Project](https://www.presidency.ucsb.edu/) website by using Requests to get information from specific urls for each presidential inaugural speech. Once the data are extracted they a saved (pickle) into txt format.

## Explore Data
The saved text document of each speech are uploaded and put into a dataframe. Each text document is labeled for the president who gave that speech. We look at the data to see what each document contain to get an understanding of text cleaning process to take.

## Clean Data
For our data we cleaned it up by:
* make all text lower case
* remove punctuations
* remove numerical values
* remove common non-sensical text (\n)
* remove urls
* tokenize text
* remove stop words

## Analyze Data
We first analyze the data by creating a word cloud of the most common words.
