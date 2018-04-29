# Project Overview

## Aim

Topic modeling is a text mining technique in which an algorithm is applied to a large corpus of documents that identifies patterns of word co-occurrence. These patterns of word co-occurrence are conceptualized as "topics" which in turn can be used to discover latent structures in the corpus, to group similar documents together, or to serve as the basis of information retrieval. While the application of topic modeling algorithms to a corpus is carried out by a computer, it is necessary for a human user to make preliminary decisions about how to prepare the corpus for modeling and how to set the parameters and hyper-parameters for the model. The aim of this project is to make recommendations for best practices for topic modeling.

## Background

Since the development of latent semantic analysis (LSA) in the 1990s (Deerwester et al., 1990) and the development of latent Dirichlet allocation (LDA) (Blei et al., 2003) in the 2000s, the literature on topic modeling has blossomed. Many of the studies which discuss the process and parameters of topic modeling are highly technical and inaccessible to the practitioner. At the same time, many of the studies authored by practitioners focus on the application of topic models without systematic exploration of how the process and parameters of topic modeling effect results of topic modeling. This project attempts to be as transparent as possible with the process and parameters of topic modeling by documenting a series experiments in building topic models in different ways from the same dataset. The results of these experiments will inform the recommendations made for best practices for topic modeling.

## Procedure

The bulk of this project is contained in a series of Jupyter notebooks, each of which contains a combination of code and discussion:
* `process_corpus.ipynb`: this notebook documents the code and decisions made in processing a large collection of scholarly articles from the *Journal of Biblical Literature* into two corpora, one a general corpus containing informative words regardless of the part of speech, the other a noun corpus containing only informative nouns.
* `build_models.ipynb`: this notebook documents the code and decisions made in building various topic models each with different parameters. 
* The remaining notebooks document the comparisons made between the various topic models generated in the above notebook.

In addition to these notebooks, this project also contains a literature review which provides an overview of recent scholarship on topic models. This review is intended to contextualize and inform the present project. Finally, the project also contains a final discussion which summarizes the results of the project and makes some recommendations for best practices for topic modeling.

## Method

This project is primarily heuristic and comparative in nature. On the basis of a single dataset (see below) a series of topic models are built using a python library called Gensim. These models are compared to see which renders the best results. The first comparison takes the number of topics and hyper-parameters as constants and compares a model based on informative words regardless of the part of speech with a model containing only informative nouns. This allows for a discussion of how eliminating parts of speech such as adjectives and verbs effect a topic model. The second comparison takes the part of speech used and hyper-parameters as constants and compares topic models built with 100, 250, and 500 topics. This allows for a discussion of how the number of topics effects a topic model. Finally, the third comparison takes part of speech used and number of topics as constants and compares topic models built with different hyper-parameters. This allows for a discussion of how hyper-parameters effect a topic model.

There are a number of different metrics used to evaluate topic models, but a very important one is the actual application of the model. With this in mind, the topic models built will be compared in terms of their ability to produce coherent topics, group documents in meaningful ways, and serve as the basis of information retrieval.

## Data

The dataset used for this project is the *Journal of Biblical Literature* (*JBL*). This is a peer-reviewed scholarly journal which focuses on the academic study of biblical literature. This dataset provides an interesting opportunity to model a relatively homogenous corpus of documents. JSTOR labs generously made the *JBL* available for this project in the form of a xml files containing metadata for each article and plain text files containing the optical character recognition full text for each article. The raw dataset contains 10,355 individual articles. A simple python script applied to the metadata files revealed 10,312 articles to be written in English, 40 to be written in German, and 3 whose language was not listed in the metadata. However, even the English articles contain quotations in German, Greek, and Hebrew (sometimes the latter two languages are transliterated). After eliminating articles which were not English or which contained peripheral matter (see  `process_corpus.ipynb`), the cropus contained 9,348 articles (which will simply be referred to as documents).


