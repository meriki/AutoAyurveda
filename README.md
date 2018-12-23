# AutoAyurveda
## Automatic extraction of drug-disease pairs from Ayurvedic Research documents

### Motivation

Medical treatment is mandated at least once in each person's life, making healthcare an important area of study. Modern medicine is synonymous with heathcare. However, treatment or cure for an ailment can be found in different ways. A study suggests that only around 20-30\% of the population in the World relies on conventional sources of medicine for treatment while rest rely on unconventional sources comprising mainly of herbal sources\cite{who}. Indian medicine dates far back. Ayurveda has been one of the most prominent forms of treatment for Indians before the introduction of modern medicine. Ayurvedic medicine is largely based on using herbal, animal and natural components present around us ranging from gold to corals. It, in fact, is the most ancient source of treatment, yet it is not elementary with its very own strong experimental and philosophical base.  \\
Ayurvedic research is prevalent today, mostly in India. Unlike Modern medicine, these research texts are not as well documented and curated for easy accessibility and information. More work is ongoing to extract relevant information from modern medical documents. This in itself is a challenging problem because of the difference in domain and variability in the research texts. We intent to do the same for Ayurvedic research documents. This poses additional challenges on top of the exisiting challenges. Some challenges are listed as follows:
- There is no comprehensive dataset mapping ayurvedic drugs and diseases like PubMed for modern medicine
- The same ayurvedic drug can be expressed under different names because of their different regional identities. They can also be in different formats (compounded or otherwise, etc.)
- Additionally the regional names are not in English to apply regular nlp models, which are trained on English texts. Additionally, no one language my encompass all the names.
- No comprehensive mapping exists from even one of their indigenous names to their modern english names, for example drug/disease names in english. 

Keeping in mind these challenges, we attempt to automate the extraction of drug-disease relations from Ayurvedic research documents. This would be a crucial step in making Ayurvedic treatment information more accessible.

We consider the problem of drug-disease identification from a research document as a Named Entity Recognition(NER) problem. We employ the use of a deep learning sequence tagger which included a BiLSTM and CRF using a combination of GloVe word Embeddings and Character embeddings. This model is a general sequence tagger. For our dataset, we downloaded a set of published papers from the renowned journals, pre processed it and curated a database by manually tagging it.We then evaluate our results using accuracy, f1-metric, precision and recall scores.

### Overview
We trained a NER deep learning model using a BiLSTM + CRF model for ayurvedic drug disease extraction. We had to manually curate our data of Ayurvedic research articles, and tag it with Drug, Disease and Function. Curated 100 train research papers and 20 test research papers. We consider the gist of the article to be in the title and abstract, so essentially one document is preprocessed title+abstract. 


### Description of the files

The ipython file can be launced in google colab. The code is explained in the notebook as comments and headings


#### Dataset format
train.words.txt : contains train documents with a space between documents to distinguish it <br/>
testa.words.txt : contains test documents in the above format<br/>
testb.words.txt : contains test documents in the above format<br />
train.tags.txt : contains space seperated NER tags for the train words above <br />
testa.tags.txt : contains space seperated NER tags for the test words above<br />
testb.tags.txt : contains space seperated NER tags for the test words above<br />
