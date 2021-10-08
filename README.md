# STR-2021: A Dataset of Semantic Textual Relatedness Created from Comparative Annotations

This repository contains data and code for the paper [STR-2021: A Dataset of Semantic Textual Relatedness Created from Comparative Annotations](www.arxiv.com).



## Dataset Description

- The dataset consists of 5500 English sentence pairs that are scored and ranked on a relatedness scale ranging from 0 (least related) to 1 (most related). 

- The sentence pairs, and associated scores, are in the file sem_text_rel_ranked.csv in the root directory. The CSV file can be read using:

  ```python
  import pandas as pd
  
  str = pd.read_csv('sem_text_rel_ranked.csv')
  
  row = str.loc[0]
  sent1, sent2 = row['Text'].split("\n")
  score = row['Score']
  ```

- Relevant columns: 

  - Text: Sentence pairs, seperated by the newline character.
  - Score: The STR score between 0 and 1. 

- Additionally, the DocID column indicates the source dataset from which the sentence pair was drawn. 


## Raw Annotations

- The `annotations/` subdirectory provides the raw MTurk annotations obtained with our comparative annotation setup.
- Each row of `annotations/bws_annotations.csv` consists of four sentence pairs along with human annotations for the most related (column `BestItem`) and the least related (column `WorstItem`) pair. 
- File `annotations/id2sents.csv` pairs each sentence pair with a corresponding ID that indicates the source dataset (see Table X of our paper).

