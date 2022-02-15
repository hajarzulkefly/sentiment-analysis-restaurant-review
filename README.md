# Sentiment-Analysis-Restaurant-Review

This project aims to explore two main approaches of sentiment analysis using lexicon-based approach vs machine learning approach as tools for opinion mining. It is conducted in Python using sklearn and gensim as the main libraries for sentiment analysis.

Download data: https://docs.google.com/spreadsheets/d/1GfjFHG8PirwieXdxaal_KU5D7VlRTe7P/edit?usp=sharing&ouid=104457313052121992878&rtpof=true&sd=true

The dataset is extracted from Google review for a restaurant located in Malaysia.

Columns: 

 > _Review_ - contains customers reviews

 > _Label_ - sentiment labels; positive or negative

In this project, I will create a framework to classify texts into two categories (positive or negative) using two approaches mentioned above. The flows are as below:

**PART 1 & PART 2 : LEXICON-BASED APPROACH**

Preprocessing steps in this section include:

**1.1 Data preparation & preprocessing**

_1.1.1 Change Label input for easier data manipulation_

 > Negative = 0

 > Positive = 1

_1.1.2 Translate Review to english language_

** Since column _Review_ contains mixed language of english and malay, it is important to translate the column into full english since most of the NLP tools are based on english language.

**1.2 Generating positive and negative lexicons list manually**

The list generated will be used to predict polarity of each review in the next part.

| Lexicon  |  Total  |
| :------: | -------:| 
| Positive | 115     |
| Negative | 174     |

**2.1 Calculate polarity**

If total score in each row is more than equal to 0, review is tagged as Positive (Label = 1).

If total score in each row is less than 0, review is tagged as Negative (Label = 0).

**2.2 Classification performance**

Performance matrix:

|         | Predicted as 0   | Predicted as 1   | Total |
| :------:| :---------:      |  :-----:         | :-----:|
| 0       | 43               | 5                | 48    |
| 1       | 1                | 81               | 82    |

Other metrics:

|          | Precision | Recall | F1-Score   | Support |
| :------: | ---------:|  -----:| ---------: | ------: | 
| 0        | 0.98      |  0.90  |      0.93  |      48 |
| 1        | 0.94      |  0.99  |      0.96  |      82 |
| Accuracy |           |        |      0.95  |     130 |

**PART 3 : MACHINE LEARNING APPROACH**

**3.1 Features comparison**

_3.1.1 Bag-of-Words_

| Model                       | Accuracy | F1-Score  | Precision | Recall | 
| :------                     | --------:| ------:   | ---------:|  -----:|
| Gradient Boosting Classifier|      0.92|      0.90 | 0.95      |  0.88  |
| Logistic Regression         |      0.88|      0.85 | 0.93      |  0.81  |
| Naive Bayes	                |      0.85|      0.78 | 0.91      |  0.75  |
| Linear Support Vector Classifier | 0.85|      0.78 | 0.91      |  0.75  |
| Neural network              |      0.81|      0.71 | 0.89      |  0.69  |
| Random Forest Classifier    |      0.77|      0.68 | 0.76      |  0.66  |
| Support Vector Machine      |      0.77|      0.63 | 0.88      |  0.62  |

_3.1.2 TF-IDF_

| Model                       | Accuracy | F1-Score  | Precision | Recall | 
| :------                     | --------:| ------:   | ---------:|  -----:|
| Gradient Boosting Classifier|      0.85|      0.78 | 0.91      |  0.75  |
| Linear Support Vector Classifier | 0.85|      0.78 | 0.91      |  0.75  |
| Naive Bayes	                |      0.81|      0.71 | 0.89      |  0.69  |
| Support Vector Machine      |      0.81|      0.71 | 0.89      |  0.69  |
| Logistic Regression         |      0.81|      0.71 | 0.89      |  0.69  |
| Neural network              |      0.77|      0.68 | 0.76      |  0.66  |
| Random Forest Classifier    |      0.77|      0.63 | 0.88      |  0.62  |

_3.1.3 Doc2vec_

| Model                       | Accuracy | F1-Score  | Precision | Recall | 
| :------                     | --------:| ------:   | ---------:|  -----:|
| Gradient Boosting Classifier|      0.85|      0.78 | 0.91      |  0.75  |
| Random Forest Classifier    |      0.77|      0.63 | 0.88      |  0.62  |
| Naive Bayes	                |      0.54|      0.71 | 0.89      |  0.69  |
| Neural network              |      0.62|      0.68 | 0.76      |  0.66  |
| Support Vector Machine      |      0.62|      0.71 | 0.89      |  0.69  |
| Linear Support Vector Classifier | 0.62|      0.78 | 0.91      |  0.75  |
| Logistic Regression         |      0.62|      0.71 | 0.89      |  0.69  |

**CONCLUSION**

| Approach         | Model                        | Feature | Accuracy | F1-Score |
| :------:         | :-----:                      | :-----: | --------:|  -----:  |
| Lexicon-Based    |            -                 |    -    |  0.95    |  0.95    |
| Machine Learning | Gradient Boosting Classifier | BOW     | 0.92     |  0.99    |


