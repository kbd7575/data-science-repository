# Movie Review Sentiment Analysis

## Problem Statement
This project builds and evaluates models to classify movie review phrases into sentiment categories. The task is challenging due to short text length and multiple sentiment classes.

## Dataset
- Source: Rotten Tomatoes movie review dataset (Kaggle)
- Size: 150,000+ phrases
- Labels: 5 sentiment classes (negative to positive)
- Challenge: Many phrases are very short (1–2 words)

## Approach

### Data Preprocessing
- Tokenization using spaCy
- Removal of punctuation and numbers
- Lemmatization
- Optional stopword removal

### Feature Engineering
- Bag of Words (BoW)
- Vocabulary size tuning (3000 vs 1500 words)
- Part-of-speech (POS) features
- Sentiment lexicon features

### Models
- Naive Bayes (baseline)
- Logistic Regression

## Experiments

1. Baseline (BoW with stopwords)
2. Stopword removal
3. Reduced vocabulary size
4. POS feature addition
5. Sentiment lexicon features
6. Logistic Regression model

## Results

| Model | Accuracy | Macro F1 |
|------|---------|----------|
| Baseline | 0.53 | 0.31 |
| Stopword Removal | 0.56 | 0.32 |
| Reduced Vocab | 0.55 | 0.35 |
| POS Features | 0.53 | 0.33 |
| Lexicon Features | 0.56 | 0.34 |
| Logistic Regression | 0.54 | 0.31 |

## Key Findings
- Removing stopwords improved performance
- Reducing vocabulary size improved F1 score
- POS and lexicon features provided limited gains
- Logistic Regression did not outperform Naive Bayes
- Models struggled with class imbalance and short text

## Repository Structure

.
├── data  
├── notebooks  
│   └── Keli_Duggar_FinalProject.ipynb  
├── report  
│   └── Keli_Duggar_FinalReport.docx  
└── README.md  

## How to Run

1. Install dependencies

pip install pandas scikit-learn spacy

2. Run Jupyter Notebook

jupyter notebook

3. Open and run

Keli_Duggar_FinalProject.ipynb

## Future Improvements
- Address class imbalance
- Use more advanced embeddings (TF-IDF, BERT)
- Try deep learning models
- Improve feature engineering
