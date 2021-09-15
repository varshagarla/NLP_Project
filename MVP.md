# Minimum Viable Product
## Title

### Goal
The goal of this project is to recommend scientific papers to a user based on the similarity of a search string or an abstract of a paper of interest.

### Data
I am using a dataset that originally contained the abstracts of ~10,000 scientific papers scraped from PubMed search results using the keywords "tobacco" and "alcohol". After subsetting on abstracts that explicitly contain the keywords (are the most relevant to the two broad topics), the dataset contains 726 abstracts with a mean abstract length of 256 words.

Before modeling, preprocessing was performed on the text, including removing punctuation and numbers, removing adverbs, removing English and a handful of custom stopwords (based on EDA), and lemmatization.

### Baseline Topic Modeling
I created baseline models using different combinations of algorithms (NMF, LSA, and LDA) and vectorizers (CountVectorizer and TF-IDF). Each baseline model included both unigrams and bigrams, and was set to output 10 topics. Of all the baseline models, the LSA with TF-IDF produced the most coherent topics, as shown below. We can see some logical groupings, such as:
- Topic 0 --> Alcohol use and mental health
- Topic 1 --> Drinking in adolescents
- Topic 7 --> Population/Demographic info
- Topic 9 --> Smoking and treatments

![Screen Shot 2021-09-15 at 9 41 54 AM](https://user-images.githubusercontent.com/87044440/133444400-0000304d-5031-47ac-b4eb-e2f58731d358.png)


### Next Steps
