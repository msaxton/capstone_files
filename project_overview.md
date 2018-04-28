### Project Overview

## Aim

Topic modeling is a text mining technique in which an algorithm is applied to a large corpus of documents that identifies patterns of word co-occurrence. These patterns of word co-occurrence are conceptualized as "topics" which in turn can be used to discover latent structures in the corpora, to group similar documents together, or serve as the basis of information retrieval. While the application of topic modeling algorithms to corpora is carried out by a computer, it is necessary for a human user to make preliminary decisions about how to prepare the corpora for modeling and how to set the parameters and hyper-parameters for the model. The aim of this project is to experiment with a number of different topic models on the same corpus and on the basis of that experiment to recommend best practices for building topic models.

## Background

Since the development of latent semantic analysis (LSA) in the 1990s (Deerwester et al., 1990) and the development of latent Dirichlet allocation (LDA) (Blei et al., 2003) in the 2000s, there have been a large amount of publications concerning technical aspects of topic modeling as well as publications concerning the application of topic modeling to specific projects such as the indexing of medical literature or the exploratory analysis of newspaper articles. In general, this body of literature tends to focus on technical aspects at the cost of application, or it tends to focus on application without systematic discussion about technical aspects. This project will contribute to the literature on topic models by providing recommendations for best practices for topic modeling.

## Procedure

In order to make recommendations for best practices for topic modeling, this project will provide a review of topic modeling literature. The goal of this review is to identify how topic models have been used in different domains (information science and the humanities) as well as the specifics of how topic models are built and implemented. This review will demonstrate that a successful topic model requires no small amount of fine tuning.

For topic models, fine tuning involves four primary areas:
1. preprocessing the documents
	 - What words need to be removed from the documents?
	 - Should documents only include a particular part of speech (i.e. nouns)?
2. processing the documents into a corpus which can be modeled
    - Which words are too frequent or too rare to include in the model?
    - Are there words which should be given more importance than other words?
3. setting the parameters for building the topic model
    - How many topics should be included in the model?
4. setting the hyper-parameters for building the model
    - How many topics should be found in a given document?
    - How many words should be found in a given topic?

## Method

