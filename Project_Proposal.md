# Unsupervised NLP Project Proposal

## Recommending Scientific Journal Articles 📗 Using NLP on Paper Abstracts 📖

Varsha Garla

### Question/need:

**Motivation:** In academia, scientific researchers rely heavily on peer-reviewed publications in scientific journals. Whether a researcher is writing a meta-analysis and needs to survey the literature on a topic; or seeking sources for background knowledge while writing an Introduction; or designing an experiment based on a similar study's Methods; or simply trying to learn more about new research being conducted in their domain of expertise... finding relevant research papers is a constant need within the research community. In practice, this is often achieved by a) searching journals using keywords, b) viewing the citations of given research paper, or c) viewing other papers that cited a given research paper. The motivation behind this project is that this can be improved using unsupervised ML and natural language processing on paper abstracts to identify other papers with similar themes.

**Objective:** Create a recommendation system to deliver relevant and related articles to a user, given a current research paper, based on the similarity of themes/topics in the abstracts.

### Data Description:
Data will be scraped from PubMed using the [metapub](https://pypi.org/project/metapub/) Python library. I aim to scrape 5,000 titles and abstracts (typically ~250 words or less) of research papers searched with the keyword "autism" or "autism spectrum disorder" (my area of undergraduate neuroscience research). I expect to extract a wide array of sub-topics under the umbrella of autism research such as genetic predisposition, behavioral therapy, sensory processing, neurimaging, etc.

### Tools:
- Webscraping: PubMedFetcher module in metapub Python library
- Data manipulation and cleaning: Pandas and Numpy
- Text precossing: NLTK, spaCy, gensim, scikit-learn
- Topic Modelling: NMF (Non-negative Matrix factorization), LDA (Latent Derilicht Analysis)
- Visualization: Tableau, pyLDAvis, matplotlib, seaborn
- Recommendation System Production: Streamlit

### MVP Goal:
The minimum viable product (MVP) will include topic modelling results, i.e. the top ten most common areas autism research featured in PubMed article abstracts. This will later be used to create a recommendation system of related research papers.
