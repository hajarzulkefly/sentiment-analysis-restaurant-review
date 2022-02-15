# sentiment-analysis-restaurant-review

This project aims to explore two main approaches of sentiment analysis using lexicon-based approach vs machine learning approach as tools for opinion mining. It is conducted in Python using sklearn and gensim as the main libraries for sentiment analysis.

Download data: https://docs.google.com/spreadsheets/d/1GfjFHG8PirwieXdxaal_KU5D7VlRTe7P/edit?usp=sharing&ouid=104457313052121992878&rtpof=true&sd=true

The dataset is extracted from Google review for a restaurant located in Malaysia.

Columns: 

  _Review_ - contains customers reviews

  _Label_ - Sentiment label; Positive or Negative

In this project, I will create a framework to classify texts into two categories (positive or negative) using two approaches mentioned above. The flows are as below:

**Part 1 & Part 2 : Lexicon-based Approach**

Preprocessing steps in this section include:

1.1 Data preparation & preprocessing

1.1.1 Change Label input for easier data manipulation:

  Negative = 0

  Positive = 1

1.1.2 Translate Review to english language

    -- Since column _Review_ contains mixed language of english and malay, it is important to translate the column into full english since most of the NLP tools are based on english language.

1.2 Generating positive and negative lexicons list manually.

The list generated will be used to predict polarity of each review in the next part.

2.1 Calculate polarity

2.2 Classification performance

**Part 3 : Machine Learning Approach**

3.1 Features comparison

3.1.1 Bag-of-Words

3.1.2 TF-IDF

3.1.3 Doc2vec

**Conclusion**

