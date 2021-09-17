# Recommending Scientific Journal Articles 📗 Using NLP on Paper Abstracts 📖
Varsha Garla

## Abstract
The goal of this project was to create a content-based scientific article recommendation system involving natural language processing and an unsupervised learning model. I worked with a dataset from Kaggle which contained hundreds of scientific paper abstracts of articles published on PubMed. After cleaning and preprocessing the text data, I used a TF-IDF vectorizer and the LSA model to create topics based on the corpus of abstracts. With these topics, I used cosine similarity between abstract topic profiles to create a content-based recommendation system that can take search words as user input or (the abstract of) a current article of interest.

## Design
Reading scientific literature is a regular task for a researcher; however, there is no optimized way to do this. When searching for relevant scientific articles, researchers must use a journal's search engine that relies on manually-entered keyword tags, or check each article that a paper either cites or is cited by. For this project, I created a content-based recommendation system which recommends articles to a researcher given a string of keywords or the abstract of an article of interest. Leveraging topic modeling and natural language processing, this provides users with articles that tag-based search results and manual citation examination alone may not allow. Another advantage is that recently published articles, that may not have been cited a lot yet, have a better chance of being discovered.

## Data
The dataset is from Kaggle and can be accessed [here](https://www.kaggle.com/sandhyaavasthi/abstractspubmed). It originally contained 10,000 abstracts of research articles on PubMed from 2015 to 2019 with the search keywords "tobacco" and "alcohol".

## Algorithms
_Cleaning_

During exploratory data analysis, I discovered that some abstracts were unrelated to "tobacco" and "alcohol". I excluded abstracts that did not explicitly contain "tobacco" or "alcohol." After this, the dataset contained 726 abstracts.

_Text Preprocessing_

Numbers and punctuation were removed from the text, which was then tokenized. After tagging the tokenized text with parts of speech, adverbs were removed and the remaining words were lemmatized.

_Topic Modeling_

Baseline models were created with different vectorizers (CountVectorizer & TF-IDF) and models (LSA, LDA, and NMF). The TF-IDF vectorizer and LSA model were eventually selected, with 9 topics, minimum document frequency of 0.01, maximum document frequency of 0.9, and custom stopwords combined with English stopwords.

_Recommendation System_

The recommendation system was built using the cosine similarity between one abstract topic profile or user search string topic profile and the other abstract topic profiles.


## Tools
- Numpy and Pandas for data manipulation
- NLTK for text processing
- Scikit-learn for preprocessing and modeling
- Matplotlib for plotting

## Communication
The findings and slide deck accompanying this project's presentation are accessible in this GitHub repository.
