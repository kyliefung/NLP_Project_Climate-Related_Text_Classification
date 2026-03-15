# NLP Project: Climate-Related Text Classification for Annual Reports

## Overview
This project investigates how Natural Language Processing (NLP) can be used to identify and classify climate-related text in annual reports. We compare four different modeling approaches to determine whether a paragraph discusses climate-related topics and, if it does, how it should be categorized in terms of sentiment, specificity, and commitment.

The project was developed in the context of the course “Natural Language Processing for Business Analytics” at Friedrich-Alexander-Universität Erlangen-Nürnberg (FAU).


## Problem Statement
Annual reports contain valuable information about how organizations address climate-related risks, opportunities, and strategic commitments. However, manually reviewing large volumes of text is time-consuming. This project explores whether NLP methods can support this process by automatically classifying climate-related paragraphs.

## Classification Tasks
The project covers four classification tasks:
- **Climate-relatedness**: whether a paragraph is climate-related or not
- **Sentiment**: whether the paragraph expresses opportunity, neutral, or risk
- **Specificity**: whether the paragraph contains specific and concrete information
- **Commitment**: whether the paragraph expresses goals, promises, or commitments

## Dataset
The labeled dataset contains:
- 400 training paragraphs
- 400 validation paragraphs
- 1 million unlabeled paragraphs used for additional experiments in data boosting
A key challenge is that the data is imbalanced, especially for the climate label. In addition, the labels sentiment, specificity, and commitment are only available when the paragraph is already labeled as climate-related. Because of this setup, the project uses macro F1-score as the main evaluation metric and applies 5-fold cross-validation for more robust evaluation.

## Approaches Compared
This project compares four NLP approaches:
- **Rule-Based NLP System**
Dictionary- and rule-based classification using handcrafted rules, WordNet expansion, and frequency-based word selection.
- **Bag-of-Words**
Traditional machine learning approaches using Bag-of-Words, TF-IDF, and n-grams with classifiers such as Logistic Regression, LASSO, Ridge, and SVM.
- **Word Embedding-Based Models**
Models based on GloVe and self-trained word embeddings, combined with different preprocessing strategies and downstream classifiers such as Logistic Regression and CNNs.
- **Transfer Learning Models**
Transformer-based models using DistilRoBERTa and ClimateBERT, including tokenizer tuning, hyperparameter tuning, and cross-validation.

## Preprocessing
Several preprocessing and feature engineering techniques were tested throughout the project, including:
- lowercasing
- stop-word removal
- stemming and lemmatization
- link removal
- alphabetic and alphanumeric token filtering
- whitespace, NLTK, and transformer tokenization

## Results
Among all approaches, transfer learning achieved the strongest overall performance. The best model was a fine-tuned ClimateBERT model, which obtained the following macro F1-scores
Climate-relatedness: 0.957
Sentiment: 0.839
Specificity: 0.882
Commitment: 0.865

Overall, the project found that:
- Rule-based models had the weakest performance
- Bag-of-Words improved substantially over rule-based methods
- Word embedding models performed better still
- Transfer learning models delivered the best results across all label

## Key Takeaways
1. Climate-related text classification can be approached effectively with modern NLP methods.
2. Transfer learning, especially domain-adapted models such as ClimateBERT, clearly outperformed traditional baselines.
3. Dataset imbalance and label dependency make macro F1-score a more suitable metric than accuracy.
4. Data preprocessing and model selection had a strong impact on performance.
