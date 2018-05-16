# Project Overview

> "All models are wrong, but some are useful" - George Box

## Aim

Topic modeling is a text mining technique in which an algorithm is applied to a large corpus of documents that identifies patterns of word co-occurrence. These patterns of word co-occurrence are conceptualized as "topics" which in turn can be used to discover latent structures in the corpus, to group similar documents together, or to serve as the basis of information retrieval. While the application of topic modeling algorithms to a corpus is carried out by a computer, it is necessary for a human user to make preliminary decisions about how to prepare the corpus for modeling and how to set the parameters and hyper-parameters for the model. The aim of this project is to make recommendations for best practices for topic modeling.

## Background

Since the development of latent semantic analysis (LSA) beginning in the 1980s (Deerwester et al., 1990) and the development of latent Dirichlet allocation (LDA) (Blei et al., 2003) in the 2000s, the literature on topic modeling has blossomed. Many of the studies which discuss the process and parameters of topic modeling are highly technical and inaccessible to the practitioner. At the same time, many of the studies authored by practitioners focus on the application of topic models without systematic exploration of how the process and parameters of topic modeling effect results of topic modeling. This project attempts to be as transparent as possible with the process and parameters of topic modeling by documenting a series experiments in building topic models in different ways from the same dataset. The results of these experiments will inform the recommendations made for best practices for topic modeling.

## Procedure

This project analyses the properties of topic models under various conditions. It begins with a literature review which introduces topic modeling, surveys select studies which have employed topic models, and discusses the decisions that must be made when building a topic model. Following the literature review, a series of analyses are offered, each of which is a combination of code and discussion. These analyses demonstrate the ways in which a topic model changes based upon how it was constructed. Finally, the project closes with a summary discussion of the findings and suggestions for best practices for the building of topic models.

## Method

 On the basis of a single dataset, a series of topic models are built using a python library called Gensim. These models are compared to see which renders the best results. The first comparison takes the number of topics and the alpha value as constants and compares a model based on informative words regardless of the part of speech with a model containing only informative nouns. This allows for a discussion of how eliminating parts of speech such as adjectives and verbs effect a topic model. The second comparison takes the part of speech used and the alpha value as constants and compares topic models built with 25, 75, and 150 topics. This allows for a discussion of how the number of topics effects a topic model. Finally, the third comparison takes part of speech used and number of topics as constants and compares topic models built with different alpha values. This allows for a discussion of how the alpha hyper-parameter affects a topic model.

There are a number of different metrics used to evaluate topic models, but a very important one is the actual application of the model. There are many potential uses for a topic model, but two important use cases are (1) to explore a large corpora of documents, often by clustering those documents in meaningful ways and (2) to serve as the basis of information retrieval. Since these use cases require the topic model to produce coherent topics, each topic model in this study will be submitted to three tests: a topic coherence test, a clustering test, and a information retrieval test.

## Data

The dataset used for this project is the *Journal of Biblical Literature* (*JBL*). This is a peer-reviewed scholarly journal which focuses on the academic study of biblical literature. This dataset provides an interesting opportunity to model a relatively homogenous corpus of documents. JSTOR labs generously made the *JBL* available for this project in the form of a xml files containing metadata for each article and plain text files containing the optical character recognition full text for each article. The raw dataset contains 10,355 individual articles. A simple python script applied to the metadata files revealed 10,312 articles to be written in English, 40 to be written in German, and 3 whose language was not listed in the metadata. However, even the English articles contain quotations in German, Greek, and Hebrew (sometimes the latter two languages are transliterated). After eliminating articles which were not English or which contained peripheral matter (see  `process_corpus.ipynb`), the corpus contained 9,348 articles (which will simply be referred to as documents).


