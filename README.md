# Micah Saxton's DU MLIS Capstone draft

## About

This repository contains files for a draft Micah Saxton's DU MLIS Capstone. The purpose of the project is to articulate "Best practices for topic modeling." Toward that end, a number of different topic models are built on a corpus of articles from the *Journal of Biblical Literature* (*JBL*) each with different parameter settings. Then, each model is evaluated on the coherence of its topics, its ability to group similar documents together, and its ability to provide useful information retrieval.

## Contents

At present the draft contains:
* a directory of a few *JBL* abstracts which are used to test the topic models’ ability to retrieve information
* a directory called "general_corpus" which contains a Gensim corpus of lemmatized *JBL* articles, a dictionary of the terms in those articles, and a number of varying models built on that corpus.
* a directory called "notebooks" which contains a number of Jupyter notebooks containing code and documentation that processed the *JBL* corpus, built various topic models, and evaluates those models
* a directory called "noun_corpus" which contains a Gensim corpus of noun-only lemmatized *JBL* articles, a dictionary of the terms in those articles, and a number of varying models built on that corpus.
* a literature review
* a project overview
* a list of references
