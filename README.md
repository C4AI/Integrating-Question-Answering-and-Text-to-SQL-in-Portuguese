# Integrating-Question-Answering-and-Text-to-SQL-in-Portuguese

Repository for the PROPOR'21 paper "Integrating Question Answering and Text-to-SQL in Portuguese"

For more information please check the paper here: https://arxiv.org/abs/2202.04048

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

In the *Datasets_Integration* folder, it is possible to find two folders that was used to integrate the datasets.

## Classifier

## BM25+PTT5

## Text-SQL 

## Integration

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