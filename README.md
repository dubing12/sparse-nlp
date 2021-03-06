# SparseNLP

## Introduction

- Word Embeddings are an important component of many language models capable of producing
 state of the art results in several NLP tasks;
- SparseNLP proposes an alternative approach for deriving word embeddings. In contrast with the tradicional dense vector representations, it creates sparse distributed representations (SDR) for each word; the representation shares the main idea of a word embedding, which was formulated by Firth in 1957: "a word is characterized by the company it keeps";
- Validation of the whole methodology is done by using these word embeddings as language models in several Natural Language Processing tasks;


## Installation

git clone https://github.com/avsilva/sparse-nlp.git

TODO:
pip install -r requirements.txt

## How to use it

In order to use SparseNLP you need your data stored in a database table with 2 columns: 
- id (int): primary key
-  cleaned_text (str): text tokens for each sentence

## Tests

- nosetests --cover-package=.\sparsenlp --with-coverage --nologcapture -x
- python -m unittest -v

  (run just one class test)
- python -m unittest -q tests.test_datacleaner.TestDataClean
- py.test -q -s tests/test_datacleaner.py::TestDataClean

 (run just one functional test)

 - python -m unittest -q tests.test_datacleaner.TestDataClean.test_ingestfiles_json_to_dict





## Project Planning

1. Training Corpora Definition - 16 Feb
2. Corpora pre-processing - 28 Feb
3. Sentence tokenization - 12 Mar
4. Sentence vetorization - 26 Mar
5. Word to sentence database - 9 Apr
6. Cluster sentences - 23 Apr
7. Word fingerprint - 4 May
8. Text fingerprint - 17 May
9. Evaluation - 30 Aug


## 1. Training Corpora Definition

Wikipedia dumps from [wikimedia 2018-01-01](https://dumps.wikimedia.org/enwiki/20180101/) 

### 1.1 Extracting plain text from Wikipedia dumps

[github - attardi/wikiextractor](https://github.com/attardi/wikiextractor)

Document files contains a series of Wikipedia articles, represented each by an XML doc element:
```markdown
<doc>...</doc>
<doc>...</doc>
...
<doc>...</doc>
```
The element doc has the following attributes:

- id, which identifies the document by means of a unique serial number
- url, which provides the URL of the original Wikipedia page.
The content of a doc element consists of pure text, one paragraph per line.

Example:
```markdown
<doc id="2" url="http://it.wikipedia.org/wiki/Harmonium">
Harmonium.
L'harmonium è uno strumento musicale azionato con una tastiera, detta manuale.
Sono stati costruiti anche alcuni harmonium con due manuali.
...
</doc>
```


## 9. Evaluation

Evaluation code repository: [github - kudkudak/word-embeddings-benchmarks](https://github.com/kudkudak/word-embeddings-benchmarks.git)
Evaluation methods: [arxiv.org/abs/1702.02170](https://arxiv.org/abs/1702.02170)

other alternative methods: [github - mfaruqui/eval-word-vectors](https://github.com/mfaruqui/eval-word-vectors)





