# Integrating-Question-Answering-and-Text-to-SQL-in-Portuguese

Repository for the PROPOR'21 paper "Integrating Question Answering and Text-to-SQL in Portuguese"

For more information please check the paper here: https://link.springer.com/chapter/10.1007/978-3-030-98305-5_26

There is also a version in arXiv: https://arxiv.org/abs/2202.04048

![Alt text]Architecture.png?raw=true "Architecture")

## Abstract

Deep learning transformers have drastically improved systems that automatically answer questions in natural language. However, different questions demand different answering techniques; here we propose, build and validate an architecture that integrates different modules to answer two distinct kinds of queries. Our architecture takes a free-form natural language text and classifies it to send it either to a Neural Question Answering Reasoner or a Natural Language parser to SQL. We implemented a complete system for the Portuguese language, using some of the main tools available for the language and translating training and testing datasets. Experiments show that our system selects the appropriate answering method with high accuracy (over 99%), thus validating a modular question answering strategy.


## Medicine Question Answering Dataset

We composed our dataset as a junction of three different datasets: MS MARCO for the factual questions and SPIDER and MIMIC SQL for SQL based questions.

### Factual Questions - Biomedicine MS MARCO Dataset

The MS MARCO dataset consists of questions that were anonymized from search queries of users of the Bing platform.

The full MS MARCO dataset: https://github.com/microsoft/MSMARCO-Question-Answering

In order to get only questions about our interest, biomedicine, we utilized the work of IBM in which separated MS MARCO between 6 different domains.

IBM domain specific extraction: https://github.com/ibm-aur-nlp/domain-specific-QA

### SQL Based questions - MIMIC SQL

SPIDER Dataset: https://yale-lily.github.io/spider

MIMICSQL Dataset: https://github.com/wangpinggl/TREQS

### Dataset preparation

In the *Datasets_Integration* folder, it is possible to find two files that were used to integrate the datasets.

## Classifier

Two different text classifiers were teste: Naive Bayes and BERTimbau. Both were trained using cross-validation and the files can be found in the Classifier folder.

## Factual Question Answering System – BM25+PTT5

We utilized a Retriever-Reader model based on the work of Cacao et al. For more information check their work: https://github.com/C4AI/deepage

The implementation of training codes can be found in the BM25-PTT5 folder. 

The system works using BM25 as the retriever and the file *Prepare_Elastic.ipynb* is used to upload the corpus in the elastic search. To prepare the questions for training PTT5, it is necessary to run *Prepare_Questions.ipynb* file.

To train PTT5, use the Train_PTT5.ipynb.


## Text-to-SQL System - mRAT-SQL

We utilized the mRAT_SQL model that can be found here: https://github.com/C4AI/gap-text2sql

## Integration and to run the system

A significant challenge is integrating these systems; each one has specific libraries, requirements and heavy computational demands. We developed a cross-platform communication scheme through the file system using a shared mount point to send and receive the questions and answers in different machines independent of their operating systems.

The files to run our architecture is in the *Final_System* folder. It is necessary to run all four files at the same time, and ask the question in the *classifier_integration.ipynb* file.

## Acknowledgments

This work was partly supported by  Itaú Unibanco S.A.  through the *Programa de Bolsas Itaú* (PBI) of the *Centro de Ciência de Dados* da Universidade de São Paulo (C2D-USP); by the Center for Artificial Intelligence (C4AI) through support from the S\~ao Paulo Research Foundation (FAPESP grant \#2019/07665-4) and from the IBM Corporation; by CNPq grants no. 312180/2018-7 and 304012/2019-0, and CAPES Finance Code 001.  

## Cite this work

```
@InProceedings{10.1007/978-3-030-98305-5_26,
author="Jos{\'e}, Marcos Menon
and Jos{\'e}, Marcelo Archanjo
and Mau{\'a}, Denis Deratani
and Cozman, F{\'a}bio Gagliardi",
editor="Pinheiro, Vl{\'a}dia
and Gamallo, Pablo
and Amaro, Raquel
and Scarton, Carolina
and Batista, Fernando
and Silva, Diego
and Magro, Catarina
and Pinto, Hugo",
title="Integrating Question Answering and Text-to-SQL in Portuguese",
booktitle="Computational Processing of the Portuguese Language",
year="2022",
publisher="Springer International Publishing",
address="Cham",
pages="278--287",
abstract="Deep learning transformers have drastically improved systems that automatically answer questions in natural language. However, different questions demand different answering techniques; here we propose, build and validate an architecture that integrates different modules to answer two distinct kinds of queries. Our architecture takes a free-form natural language text and classifies it to send it either to a Neural Question Answering Reasoner or a Natural Language parser to SQL. We implemented a complete system for the Portuguese language, using some of the main tools available for the language and translating training and testing datasets. Experiments show that our system selects the appropriate answering method with high accuracy (over 99{\%}), thus validating a modular question answering strategy.",
isbn="978-3-030-98305-5"
}
```