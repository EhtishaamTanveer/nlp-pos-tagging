# POS Tagging with Hidden Markov Models and the Viterbi Algorithm

This repository contains the code and resources for a Part-of-Speech (POS) tagging project using Hidden Markov Models (HMMs) and the Viterbi algorithm. The project utilizes a corpus from the Wall Street Journal (WSJ) for training and evaluation.

## Project Overview

Part-of-Speech tagging is the process of assigning grammatical tags (like noun, verb, adjective, etc.) to each word in a sentence. This project implements a statistical approach using HMMs, which are probabilistic models that excel at modeling sequential data. The Viterbi algorithm is employed for efficient decoding, finding the most likely sequence of POS tags given an input sentence. 

Complete list of the tags assigned in the process are given [here](http://relearn.be/2015/training-common-sense/sources/software/pattern-2.6-critical-fork/docs/html/mbsp-tags.html) 

## Project Characteristics

Main tasks performed in this NLP project are:

1. **HMM Training:** Estimating transition probabilities (probability of moving from one POS tag to another) and emission probabilities (probability of a word given a POS tag) from the training data.
2. **Smoothing:** Add-k smoothing is implemented in the probability matrices to avoid divison by 0.
3. **Viterbi Decoding:** Implementing the Viterbi algorithm to find the most likely sequence of POS tags for a given input sentence. (Dynamic Programming Approach)
4. **Evaluation:** Calculating *accuracy* metrics on the test data.
   
## Repository Structure

* nlp-pos-tagging.ipynb: Main jupyter notebook containing the project code.
* utils_pos: All the helper functions are saved in the utility file.
* w2_unittest: All test cases are saved in this file to check the correctness of functions created in main file.
* data/
  * WSJ_02-21.pos: Training Corpus
  * WSJ_24.pos: Testing Corpus
  * hmm_vocab.txt: Vocabulary words taken from training set that have appeared two or more times
  * test.words: Preprocessed Test Corpus
* support_files/: The files in this folder are used in deriving test cases
  * best_paths_initilized.pkl
  * best_paths_trained.pkl
  * best_probs_initilized.pkl
  * best_probs_trained.pkl

## Dependencies

The project requires the following Python libraries:

- pandas
- collections
- math
- numpy

You can install them using pip:

```bash
pip install pandas collections math numpy
```

## Example

Given the input sentence: "The cat sat on the mat.", the POS tagger might output:

The/DT cat/NN sat/VBD on/IN the/DT mat/NN

Where:

  - DT: Determiner
  - NN: Noun
  - VBD: Verb (past tense)
  - IN: Preposition
  
## Further Improvements

* **Backoff Models:** Explore backoff models to handle cases where there is insufficient data for certain transitions or emissions.
* **More Sophisticated Features:** Incorporate more sophisticated features beyond simple word/tag pairs (e.g., prefixes, suffixes, capitalization).
* **Evaluation Metrics:** Consider additional evaluation metrics beyond accuracy, such as precision, recall, and F1-score.

## Acknowledgements

  * [Wall Street Journal](https://www.wsj.com/)
  * [Coursera](https://www.coursera.org/)
