# Minimum Viable Product
## Recommending Scientific Journal Articles 📗 Using NLP on Paper Abstracts 📖

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
- **Number of Topics**: While the LSA + TF-IDF model yielded the most promising results, I am curious to see if increasing the number of topics will produce more coherent topics.
- I will likely stick with the LSA model and try to improve it
- **Bigrams**: As shown, many of the topics top terms have overlap of unigrams and bigrams (i.e. Topic 8 "substance" and "substance abuse", Topic 6 "mental health" and "mental". Since bigrams capture more meaning, I would like to experiment with only using bigrams to see how the topics and top terms change.
- **Stemming**: I have only lemmatized the text. However, the topics may benefit from stemming, as shown in the initial results (i.e. Topic 1 "adolescence" and "adolescent", Topic 5 "drink" and "drinking")
- **More custom stop words**: While I did some initial removal of custom stop words, I want to look at the vocabulary of the abstracts to see if I can remove any more fluff words that don't add meaning, since some are polluting the top terms of the topic results (i.e. suggest, determine, report, associate). This may help in finding more meaning and extracting latent topics that are being obscured by unnecessary terms. In a similar line of thinking, I may tune the min_df and max_df hyper parameters to experiment with the rarity/popularity of terms allowed in modeling.
