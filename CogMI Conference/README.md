# ProcessData.ipynb

This file cleans up and procecess the two tweetset.csv datasets so that they can be imported and used with the machine learning models

processed_1.csv is generated from this file by processing tweetset_1.csv

processed_2.csv is generated from this file by processing tweetset_2.csv

# FeatureExtraction.ipynb

This file creats 8 different NLP vectorizations for 4 different scenarios

The four scenarios are:

1) Training Data and Testing Data come from processed_1.csv (stratified 80/20 split)
2) Training Data and Testing Data come from processed_2.csv (stratified 80/20 split)
3) Training Data is processed_1.csv and Testing Data is processed_2.csv
4) Training Data is processed_2.csv and Testing Data is processed_1.csv

The eight NLP schemes are:

1) Unigrams with frequency counts
2) Unigrams with Tf-idf scores
3) Bigrams with frequency counts
4) Bigrams with Tf-idf scores
5) Reduced Frequency Unigrams
6) Reduced Tf-idf Unigrams
7) Reduced Frequency Bigrams
8) Reduced Tf-idf Bigrams

The unigrams and bigrams are generated with roughly the top 80% most frequently occuring unique features to remove low-occuring features from the data. This should allow the trained models to focus on the most significant features.

The reduced unigrams and bigrams are sparse reductions that are 5% the size of the corresponding NLP vectors.

Warning: Running this entire file and saving every subsequent NLP vector will take up a lot of storage (well over 100 GB). It is recommended that only 8 of the vectorizations corresponding to 1 specific scenario are run and saved at a time. That data should be used to train, evaluate, and save several machine learning models and then should be deleted before starting on another scenario to conserve space.

# Scenario.ipynb Files

The four files (Scenario 1, Scenario 2, Scenario 3, Scenario 4) correspond to the four scenarios outlined in the FeatureExtraction File. 

The FeatureExtraction File generates and saves the 8 NLP schemes and the labels for each scenario. Then, in the scenario files, the 8 vectorizations and correct labels are imported. Four classifiers are built and evaluated for each of the 8 NLP schemes.

The four classifiers are:

1) Logistic Regression
2) Random Forest
3) Deep Neural Network
4) Deep Neural Network with Early Stopping

The evaluation metrics for the classifiers are:

1) Accuracy
2) ROC AUC Score
3) F1 Score
4) Precision
5) Recall

Warning: Running the entire Scenario file for some of the scenarios may cause the kernel to crash at the Bigram/Tf-idf Bigram classifiers. It is recommended that those sections are run independently of each other and all the other NLP schemes through kernel resets.

# WordCloud.ipynb

This file generates Word Clouds for the datasets to show the distribution of words in the corpus

# FeatureStatistics.ipynb

This file generates informative statistics and visualizations highlighting key characteristics of the datasets
