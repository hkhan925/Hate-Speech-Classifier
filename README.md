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
    from sklearn._______ import _______

The `pandas` package is utilized for working with comma-separated values (.csv) files. The `numpy` package is used for array processing for data pulled from the .csv files. The `matplotlib.pyplot` package allowed for the visual presentation of descriptive data staistics. The `nltk` package's `stopwords` and `PorterStemmer` methods allowed for the removal of stopwords and the stemming of words when cleaning the data. The `wordcloud` package allowed for the visual representation of the text data for each individual class of the data set. The `sklearn` (scikit-learn) package provided the methods for feature extraction 

### <u>Data Specifications</u>
The annotated (manually labeled) data is obtained from Crowdflower (<a href="https://data.world/crowdflower/hate-speech-identification">https://data.world/crowdflower/hate-speech-identification</a>). Annotated data is utilized for the ability to train the classifiers on the set of tweets that are manually labeled/classified into the specified classes. 

The data set consisted of 14,509 tweets annotated as 7,274 neutral tweets, 4,836 offensive tweets, and 2,399 hate tweets. In this projec, the tweets were assigned binary classifications of neutral speech (1) and hate/offensive speech (2).

#### Sample of Data Before Preprocessing

| tweet_text | confidence | tweet_class |
| ---------- | ---------- | ----------- |
| Warning: penny boards will make you a faggot      | 0.6013 | 1 |
| Fuck dykes	                                    | 0.7227 | 2 |
| @sizzurp__ @ILIKECATS74 @yoPapi_chulo @brandon...	| 0.5229 | 2 |
| "@jayswaggkillah: "@JacklynAnnn: @jayswaggkill...	| 0.5184 | 2 |
| @Zhugstubble You heard me bitch but any way I'... | 0.5185 | 1 |
| ... | ... | ... |

#### Sample of Data After Preprocessing

| tweet_text | confidence | tweet_class |
| ---------- | ---------- | ----------- |
| warn penni board make faggot                      | 0.6013 | 1 |
| fuck dyke                                         | 0.7227 | 2 |
| least look like jefre star...                     | 0.5229 | 2 |
| fag jacki jealou neeeee                           | 0.5184 | 2 |
| heard bitch way back th texa wtf talk bitc...     | 0.5185 | 1 |
| ... | ... | ... |

### <u>Program Specifications</u>
1. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Preliminary%20Analysis.ipynb">Preliminary Analysis</a> and <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Preliminary%20Statistics.ipynb">Preliminary Statistics</a> - Preliminiary analysis of the data set involved ensuring no NULL values were present. An initial collection of statistics revealed, by class, the average length of the tweets, the percentage of tweets that included a user tag, and the percentage of tweets that contained a URL link. Such statistics shed light on issues that could affect the data preprocessing (i.e. the necessary removal of the arbitrary user tags and URL links).

2. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Preprocessing%20Data.ipynb">Preprocessing Data</a> and <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Stemming%20Words.ipynb">Stemming Words</a> - For preprocessing the data, all of the tweets were converted into lowercase letters and all punctuation marks and extra whitespaces were removed. The hashtag symbol was removed from hashtags to analyze the hashtag as a word itself. Encoding the tweets to text caused the emojis to be read in as random symbols - so, each tweet was iterated through to ensure that only characters that were present in a pre-defined valid characters list remained in each tweet. The user tags (i.e. any word containing an '@' symbol) were replaced with '[@]' and links (i.e. words that contained 'https://') were replaced with '[LINK]' to allow easy and quick filtering of all user tags and links when removing uninformative words. Utilizing the `nltk` package, stopwords were removed to remove the uninformative words; and, the text in each of the tweets was normalized by stemming each of the words. Stemming the words caused some tweets to be empty, or even become duplicate tweets, so the tweets were iterated through to filter out any empty or duplicate tweets.

3. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Building%20Word%20Clouds.ipynb">Building Word Clouds</a> - Building a word cloud is a good way to visualize natural language data. The size of each word in the word cloud indicates the frequency with which the word occurs in the data set. Utilizing the `wordcloud` package, word clouds were generated for each class, and any frequently appearing uninformative words became clearly identifiable. Iterating through the removal of such uninformative words and generating the word clouds provided a more finely tuned data set.

4. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Descriptive%20Statistics.ipynb">Descriptive Statistics</a> and <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Confidence%20Score%20%26%20Statistics.ipynb">Confidence Scores & Statistics</a> - The frequency and distribution of unique words categorized by class were computed and displayed to provide a descriptive statistical analysis of the data set. Such an analysis provided a good overview of the overall content of the dataset, showing content that suited the purposes of this project, which boosted the reliability of the dataset. Using the confidence scores from the data set, a visual representation of the distribution of the confidence scores of each class was produced, along with the average confidence for each class. This provided a baseline accuracy to estimate the resulting accuracy of the trained models.

5. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Feature%20Extraction.ipynb">Feature Extraction</a> - Feature extraction vectorizes the text in such a way that key features of the text, such as the semantic meaning and context of the words and sentences, are numerically represented in high-dimensional vectors. The methods used were implementations of a unigram and of a bigram; the term frequency-inverse document frequency (TF-IDF) score; and the Skip-Gram Word2Vec word embedding. Once the data set was encoded using each implementation, the TruncatedSVD method from the `sklearn.decomposition` package allowed for dimensionality reduction, which was applied to only the unigram, bigram, and TF-IDF sparse matrices.

6. <a href="https://github.com/amar-sinha/Hate-Speech-Classifier/blob/master/Machine%20Learning%20Models.ipynb">Machine Learning Models</a> - 

    i. 

    ii.

    iii.

    iv.