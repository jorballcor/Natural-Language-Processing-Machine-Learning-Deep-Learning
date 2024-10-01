# TF-IDF and N-Grams Model - README

## Overview

This notebook implements two key techniques used in text processing and Natural Language Processing (NLP):
1. **TF-IDF (Term Frequency-Inverse Document Frequency)**
2. **N-Grams** for capturing word sequences

### 1. TF-IDF Model

TF-IDF is a numerical statistic used to evaluate how important a word is to a document in a collection or corpus. It is an enhancement over the Bag of Words model, as it considers not just the frequency of a word in a document but also how rare or common the word is across all documents in the corpus.

#### Key Concepts of TF-IDF:
- **Term Frequency (TF)**: Measures how frequently a term occurs in a document. Higher frequency implies greater importance within the document.
- **Inverse Document Frequency (IDF)**: Measures how important a term is by considering how rare or common the term is across the entire corpus. Rare words across documents are given more weight than common ones.

The TF-IDF score for a word is computed as:
  
TF-IDF(t, d) = TF(t, d) * IDF(t)
Where:
- \( t \) is the term,
- \( d \) is the document.

#### Steps in the Notebook:
1. **Text Preprocessing**:
   - Tokenization, lowercasing, and removing stop words or special characters.
   
2. **TF-IDF Computation**:
   - For each document, the term frequencies and inverse document frequencies are calculated, and then the TF-IDF score is computed.
   
3. **Visualization**:
   - The distribution of TF-IDF scores across documents is visualized.

#### When to Use TF-IDF:
- **When Word Importance Matters**: TF-IDF is great when you need to capture the relative importance of words. It’s widely used in tasks like text classification, information retrieval, and summarization.
- **When Working with Large Corpora**: It helps to differentiate between common and rare words, which is useful for larger corpora where common words like "the" or "is" can dominate in simple frequency models.
- **Feature Extraction**: TF-IDF serves as a useful feature extraction technique for machine learning models in NLP.

#### Limitations:
- **Still Ignores Word Order**: Like BoW, TF-IDF doesn’t account for the sequence of words or any syntactical relationships.
- **Sparse Representation**: It still results in sparse matrices for large vocabularies, leading to computational challenges.

---

### 2. N-Grams Model

An **N-Gram** is a contiguous sequence of `N` items (words or characters) from a given sequence of text. It captures some word context and provides a way to represent word relationships, unlike BoW or TF-IDF, which treat words independently.

#### Key Concepts of N-Grams:
- **Unigrams**: Single words, similar to BoW.
- **Bigrams**: Sequences of two consecutive words.
- **Trigrams**: Sequences of three consecutive words.

By capturing pairs or triples of words, N-Grams allow us to consider simple contextual information, like phrases or common word combinations.

#### Steps in the Notebook:
1. **Text Preprocessing**:
   - Tokenization and cleaning.
   
2. **N-Grams Representation**:
   - Convert the text into bigrams or trigrams to capture simple context between words.
   
3. **TF-IDF with N-Grams**:
   - Combine N-Grams with TF-IDF to get the importance of word sequences, improving upon simple word frequency models.

#### When to Use N-Grams:
- **Phrase Detection**: When you want to capture more information than just single words, like detecting key phrases or multi-word expressions.
- **Context-Aware Models**: Useful in language models, auto-complete features, or any task where word combinations are important.
- **Improving Classification Accuracy**: For some tasks, using bigrams or trigrams in conjunction with TF-IDF can improve classification performance by including word order information.

#### Limitations:
- **Computational Complexity**: Using bigrams, trigrams, or higher-order N-Grams increases the size of the feature space exponentially.
- **Not Very Deep**: While N-Grams capture some context, they don’t fully capture long-term dependencies or semantics of the text, which more advanced techniques like word embeddings or neural networks address.

### Conclusion:

This notebook demonstrates how TF-IDF and N-Grams can improve text representation for downstream tasks such as text classification or clustering. These techniques are useful when simple BoW is too simplistic but advanced neural models are not necessary.

