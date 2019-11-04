Hate Speech Classifier

Packages Used:
1) pandas
2) numpy
3) matplotlib
4) nltk

Order of Files:

1) Preliminary Analysis
    - Changes Column Names
    - Makes Labels numerical
    - Rearranges Columns
    - Saves changes into "altered_hate_speech.csv"
    
2) Preliminary Statistics
    - Calculates and graphs average length of tweets by class
    - Calculates and graphs number of @'s of tweets by class
    - Calculates and graphs number of tweets containng a link by class

3) Preprocessing Data
    - Makes all tweets lowercase
    - Removes extra whitespace
    - Removes punctuation
    - Removes hashtag characters
    - Removes garbage characters that were not properly rendered
    - Replaces all instances of twitter handles
    - Reaplces all instances of a link
    - Saves changes into "processed_hate_speech.csv"
    - Calculates frequency of unique words by class

4) Stemming Words
    - Removes stop words, slang words, and contractions
    - Stems words using nltk PorterStemmer
    - 

We're going to want instructions on how to navigate the files and a description of the actual project here

This doesn't have to be completed at the time of the midterm, but by the Final, I think it should look pretty and have all the charts, wordclouds, figures, and results we're going to put in the final report
