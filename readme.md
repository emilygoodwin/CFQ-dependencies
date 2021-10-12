# Dependencies for CFQ 

## Dataset
The `parsed-CFQ-corpus.conllu` file contains dependency parses for the entire CFQ dataset, in [CONLL-U format](https://universaldependencies.org/format.html) 

Note that there is only arcs and arc labels: no POS tags, morphological features or lemmmas etc. For the experiments in the paper, a dummy POS tag was inserted.

## Syntactic Constructions
`SubtreesBySentence.pkl` Contains a dictionary with each sentence and the subtrees it contains. 
`SubtreesByStructure.pkl` Contains a dictionary with each subtree, and the sentences in the dataset which contain it. 

## Evaluation 
To get the Whole Sentence Content-word Labeled Attachment Score, use `conll18_ud_eval.py`. 
This script is adapted from the 2018 version of the [CoNLL 2018 Shared Task Evaluation Script](https://universaldependencies.org/conll18/evaluation.html). It has been modified to calculate the percentage of sentences in the test set which have all `content word' arcs correctly labeled. 

Usage:
```bash
conll18_ud_eval.py path/to/gold/parses path/to/predicted/parses
```