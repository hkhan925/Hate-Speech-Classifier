# Hate Speech Classifier

### <u>Goal and Motivation</u>
This repository hosts a machine learning model for hate speech classification. The goal is to process and classify tweets as instances of hate speech or not, motivated by the idea that identifying hate speech content for removal will help cultivate safer and healthier spaces on social media platforms.

### <u>Implementation</u>
The process of cleaning and preparing data and the application of the machine learning algorithms are implemented in Python scripts run in Jupyter Notebook. Each notebook file provides the functions written for a specific part of each major step in the process of cleaning and analyzing the data.

### <u>Packages</u>

    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    import nltk
    from wordcloud import WordCloud

The `pandas` package is utilized for working with comma-separated values (.csv) files. The `numpy` package is used for array processing for data pulled from the .csv files. The `matplotlib.pyplot` package allowed for the visual presentation of descriptive data staistics. The `nltk` package's `stopwords` and `PorterStemmer` methods allowed for the removal of stopwords and the stemming of words when cleaning the data. The `wordcloud` package allowed for the visual representation of the text data for each individual class of the data set.

### <u>Data Specifications</u>
The annotated (manually labeled) data is obtained from Crowdflower (<a href="https://data.world/crowdflower/hate-speech-identification">https://data.world/crowdflower/hate-speech-identification</a>). Annotated data is utilized for the ability to train the classifiers on the set of tweets that are manually labeled/classified into the specified classes. 

The data set consisted of 14,509 tweets annotated as 7,274 neutral tweets, 4,836 offensive tweets, and 2,399 hate tweets. In this projec, the tweets were assigned binary classifications of neutral speech (0) and hate/offensive speech (1).

> Sample of Data Before Preprocessing

| tweet_text | confidence | tweet_class |
| ---------- | ---------- | ----------- |
| Warning: penny boards will make you a faggot      | 0.6013 | 1 |
| Fuck dykes	                                    | 0.7227 | 2 |
| @sizzurp__ @ILIKECATS74 @yoPapi_chulo @brandon...	| 0.5229 | 2 |
| "@jayswaggkillah: "@JacklynAnnn: @jayswaggkill...	| 0.5184 | 2 |
| @Zhugstubble You heard me bitch but any way I'... | 0.5185 | 1 |

> Sample of Data After Preprocessing

| tweet_text | confidence | tweet_class |
| ---------- | ---------- | ----------- |
| warn penni board make faggot                      | 0.6013 | 1 |
| fuck dyke                                         | 0.7227 | 2 |
| least look like jefre star...                     | 0.5229 | 2 |
| fag jacki jealou neeeee                           | 0.5184 | 2 |
| heard bitch way back th texa wtf talk bitc...     | 0.5185 | 1 |

### <u>Program Specifications</u>
1. _Preliminary Analysis and Statistics_ - Preliminiary analysis of the data set involved ensuring no NULL values were present. An initial collection of statistics revealed, by class, the average length of the tweets, the percentage of tweets that included a user tag, and the percentage of tweets that contained a URL link. Such statistics shed light on issues that could affect the data preprocessing (i.e. the necessary removal of the arbitrary user tags and URL links).

2. _Preprocessing Data_ - For preprocessing the data, all of the tweets were converted into lowercase letters and all punctuation marks and extra whitespaces were removed. The hashtag symbol was removed from hashtags to analyze the hashtag as a word itself. 

    Encoding the tweets to text caused the emojis to be read in as random symbols - so, each tweet was iterated through to ensure that only characters that were present in a pre-defined valid characters list remained in each tweet. 

    The user tags (i.e. any word containing an '@' symbol) were replaced with '[@]' and links (i.e. words that contained 'https://') were replaced with '[LINK]' to allow easy and quick filtering of all user tags and links when removing uninformative words.

    Utilizing the `nltk` package, stopwords were removed to remove the uninformative words; and, the text in each of the tweets was normalized by stemming each of the words. Stemming the words caused some tweets to be empty, or even become duplicate tweets, so the tweets were iterated through to filter out any empty or duplicate tweets.

3. _Building Word Clouds_ - 

4. _Descriptive Statistics_ - 

5. _Preprocessing to Compute Language Features_ - 

6. _Feature Extraction_ - 

7. _Machine Learning Models_ - 

    i. 

    ii.

    iii.

    iv.