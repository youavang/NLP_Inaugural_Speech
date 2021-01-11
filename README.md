# Inaugural Speech Analysis with NLP

We used NLP techniques to analyze presidential inaugural speeches and compare them in several ways. We analyzed the past four presidents' first inaugural speeches by comparing their word cloud, total unique words, total words per speech, their overall sentiment, their sentiment throughout the speech, and defining the topic of their speech. The steps we took for this project was 1) collect data, 2) explore data, 3) clean data 4) analyze data, 5) find sentiment, and 6) topic modeling.

## Collect Data
We used BeautifulSoup to collect data from [The American Presidency Project](https://www.presidency.ucsb.edu/) website by using Requests to get information from specific urls for each presidential inaugural speech. Once the data are extracted they a saved (pickle) into txt format.
![get data](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/get_data.png)

## Explore Data
The saved text document of each speech are uploaded and put into a dataframe.  
![data frame](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/dataframe.png)

Each text document is labeled for the president who gave that speech. We look at the data to see what each document contain to get an understanding of text cleaning process to take.
![speech](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/speech.png)

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
![word cloud](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/wordcloud.png)

Next, we aggregate the total amount of unique words spoken by each president and we aggregate the total words spoken per speech, then create a bar chart to visualize the totals.
![total](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/bar.png)

## Find Sentiment
We analyzed the sentiment of each inaugural speech by using TextBlob by labeling how polar and subjective each word is in each speech. Polarity labels how positive or negative a word is on a range of -1 (very negative) to 1 (very positive). Subjectivity labels how factual or opinionated a word is on a range of 0 (factual) to 1 (opinion).

First, we analyze the over all sentiment of an inaugural speech given by each president.
![overall sentiment](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/overallsentiment.png)

Next, we analyze the sentiment of each inaugural speech over the entire speech.
![time sentiment](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/timesentiment.png)

## Topic Modeling
We use Latent Dirichlet Allocation (LDA) modeling to find the various topic in our data. First, we created a document-term matrix (corpus), then we create a dictionary (terms) that we need to pass into our models. Next, we tested the LDA model with all the text in the corpus and the topics didn't really make much sense.
![corpus all](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/corpus_all.png)

The second LDA model was created with only nouns in the corpus and the topics makes more sense.
![corpus noun](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/corpus_noun.png)

The third LDA model was created with nouns and adjectives in the corpus.
![corpus noun+adj](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/corpus_na.png)

We tried to improve our models by selecting different number of topics and passes before settling on four topics and passing the corpus through the model a thousand times. We also compare the perplexity of each model to see which one was the best. 
![perplexity](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/perplexity.png)

Perplexity measure how well a model predicts a sample. In general, the smaller the perplexity (closer to 0), the better the prediction. Based on the perplexity values of our models, the LDA model with only nouns has the smallest value and ,hence, is the best model.

Next, we try to match each topic to a president and this is what we got.
![topic-president](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/topic-president.png)

We also look at the word clouds to help us find the best topic name for each topic.
![word cloud](https://github.com/youavang/NLP_Inaugural_Speech/blob/main/images/wordcloud.png)

Based on our analysis, we conclude that topic 0 story, topic 1 is idea, topic 2 is dream, and topic 3 is spirit.

 Topic | Topic Name | President 
 --- | --- | --- 
  0 | story | George W. Bush 
  1 | idea | Bill Clinton 
  2 | dream | Donald Trump 
  3 | spirit | Barck Obama 
  

