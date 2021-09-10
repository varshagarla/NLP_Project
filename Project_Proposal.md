# Unsupervised NLP Project Proposal

## Recommending Scientific Journal Articles 📗 Using NLP on Paper Abstracts 📖

Varsha Garla

### Question/need:

**Motivation:** In academia, researchers rely heavily on peer-reviewed publications in scientific journals. As a student researcher, reading literature was critical for developing domain knowledge in the area of my lab's study, which was sensory processing in infants with a higher familial predisposition for being diagnosed with autism. While my lab relied on a few key research papers that established foundational theories in the field, I still had to find other research papers that were related to or supported the work we were doing when writing new papers or simply trying to learn more about the landscape of research at large. Often, finding relevant articles involved performing searches with different keywords in journals or finding other papers that a particular paper cited or was cited by. This process can lead you down a rabbit hole hunting for helpful papers and sometimes even after doing so, upon reading the abstract, you may realize that a paper is barely relevant to the topic you were interesed in. This can be improved using unsupervised machine learning. Instead of manually perusing through search results and citations, natural language processing on abstracts can identify the topics and similarities across many abstracts/papers in a journal.

**Objective:** Create a recommendation system to deliver relevant and related articles to a user, given a current research paper, based on the similarity of themes/topics in the abstracts.

### Data Description:
Data will be scraped from PubMed using the [metapub](https://pypi.org/project/metapub/) Python library. I aim to scrape 5,000 titles and abstracts (typically ~250 words or less) of research papers searched with the keywords "autism" or "children autism". I expect to extract a wide array of sub-topics under the umbrella of autism research such as genetic predisposition, behavioral therapy, sensory processing, neuroimaging, molecular biology, etc.

Update: I am still trying to get this to work but if I am unable to scrape the abstracts by the end of the day today, I will use [this dataset](https://www.kaggle.com/sandhyaavasthi/abstractspubmed) from Kaggle that contains 10,000 abstracts of research articles from 2015 to 2019 with the search keywords "tobacco" and "alcohol".

### Tools:
- Webscraping: PubMedFetcher module in metapub Python library
- Data manipulation and cleaning: Pandas and Numpy
- Text precossing: NLTK, spaCy, gensim, scikit-learn
- Topic Modelling: NMF (Non-negative Matrix factorization), LDA (Latent Derilicht Analysis)
- Visualization: Tableau, pyLDAvis, matplotlib, seaborn
- Recommendation System Production: Streamlit

### MVP Goal:
The minimum viable product (MVP) will include topic modelling results, i.e. the top ten most common areas of autism research featured in PubMed article abstracts. This will later be used to create a recommendation system of related research papers for the final product.
