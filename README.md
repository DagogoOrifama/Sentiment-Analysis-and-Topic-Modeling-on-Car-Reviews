# Deciphering User Views from Car Reviews using Text Mining, Predictive Modeling, and Topic Summarization 

This project involves text mining, sentiment analysis, predictive modeling, and topic summarization on car review datasets from Edmunds and TripAdvisor. The goal is to understand user sentiments towards different car models and determine the top three vehicles based on user opinions.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Data Exploration and Preparation](#data-exploration-and-preparation)
- [Model Design and Implementation](#model-design-and-implementation)
- [Analysis and Discussion](#analysis-and-discussion)
- [Data Privacy, Ethical, and Legal Issues](#data-privacy-ethical-and-legal-issues)
- [Conclusion](#conclusion)
- [References](#references)

## Introduction

In the era of big data, understanding user-generated content is crucial for informed decision-making. This research uses car review datasets from Edmunds and TripAdvisor, covering model years 2007 to 2009, to explore sentiment analysis and topic modeling. The objective is to determine the top three vehicles based on user opinions, providing valuable insights to the automotive sector and aiding customer decision-making.

## Dataset

The dataset includes user-generated reviews of cars from Edmunds and TripAdvisor for the 2007, 2008, and 2009 model years. Each review contains details such as name, model, date, author, comment, and favorites. The dataset is organized into three directories: 2007, 2008, and 2009, with reviews for individual cars in each file.

[Dataset Source](https://archive.ics.uci.edu/dataset/205/opinrank+review+dataset)

## Data Exploration and Preparation

1. **Initial Exploration**:
    - Viewed top and bottom rows using `head()` and `tail()`.
    - Summarized data types and checked for missing values with `info()` and `isnull().sum()`.
    - Displayed statistical summaries using `describe()`.

2. **Data Cleaning**:
    - Added file extensions to XML files.
    - Extracted semi-structured data into a DataFrame.
    - Ignored null values in the Date, Author, and Favorite columns since the Comment column had no null values.

3. **Text Preprocessing**:
    - Converted text to lowercase.
    - Removed non-alphanumeric characters.
    - Tokenized text into words.
    - Lemmatized words to their base forms.
    - Removed stopwords.
    - Applied preprocessing to the Comment column and stored results in a new column, `Processed_Comment`.

4. **Exploratory Data Analysis**:
    - Visualized the distribution of comments using bigrams and trigrams to compare raw and processed text.

## Model Design and Implementation

1. **Sentiment Analysis**:
    - Used the VADER sentiment analyzer to classify comments as positive or negative.
    - Generated sentiment scores with the `SentimentIntensityAnalyzer`.

2. **Predictive Modeling**:
    - Split the dataset into training and test sets.
    - Applied TF-IDF Vectorizer for text encoding.
    - Balanced the dataset using SMOTE oversampling.
    - Trained a Multinomial Naive Bayes classifier.
    - Developed a function to predict sentiment from raw comments, saving the model and vectorizer for future use.

3. **Topic Modeling and Summarization**:
    - Used TF-IDF Vectorizer to transform comments into TF-IDF features.
    - Applied Latent Dirichlet Allocation (LDA) to identify topics in the comments.

## Analysis and Discussion

- **Sentiment Analysis**:
    - Majority of comments were positive.
    - Identified top three cars based on positive sentiment: Volvo S40 2008, followed by other highly-rated models.
    - Visualized word clouds for top-rated cars to highlight user preferences.

- **Predictive Modeling**:
    - Achieved over 90% accuracy with the Multinomial Naive Bayes classifier.
    - Evaluated model performance using confusion matrices.

- **Topic Summarization**:
    - Identified recurring themes about cars, attributes, problems, and experiences.
    - Provided insights into why users preferred certain models.

## Data Privacy, Ethical, and Legal Issues

- Ensured ethical use of data, complying with privacy laws and maintaining data integrity.
- The dataset is licensed under the Creative Commons Attribution 4.0 International license, allowing use for research purposes with appropriate credit.

## Conclusion

This study explored sentiment analysis, predictive modeling, and topic summarization on car review datasets. The analysis provided valuable insights into user sentiments and preferences, identifying top-rated car models and highlighting key attributes. The results demonstrate the power of data science in extracting meaningful patterns and aiding decision-making in the automotive industry.

## References
- Nama, V., Hegde, V., & Babu, B. S. (2021). Sentiment Analysis of Movie Reviews: A Comparative Study between the Naive-Bayes Classifier and a Rule-based Approach. 2021 International Conference on Innovative Trends in Information Technology (ICITIIT).
- OpinRank Review Dataset. (2011). UCI Machine Learning Repository. doi:https://doi.org/10.24432/C5QW4W
