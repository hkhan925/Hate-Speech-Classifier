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
The annotated (manually labeled) data is obtained from Crowdflower (<a href="https://data.world/crowdflower/hate-speech-identification">https://data.world/crowdflower/hate-speech-identification</a>). Annotated data is utilized for the ability to train the classifiers on the set of tweets that are manually labeled/classified into the specified classes. The hate and offensive speech data in this project have been assigned binary classifications of neutral speech (0) and hate/offensive speech (1).

### <u>Program Specifications</u>
1. Preliminary Analysis

2. Preliminary Statistics

3. Preprocessing Data

4. Stemming Words

5. 