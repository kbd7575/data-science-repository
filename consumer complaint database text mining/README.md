# Consumer Complaint Classification

## Problem Statement
The Consumer Financial Protection Bureau receives a large volume of consumer complaints across financial products. Manually categorizing these complaints is time-consuming and resource-intensive. This project builds models to automatically classify complaint narratives into product categories.

## Dataset
- Source: CFPB Consumer Complaint Database
- Filtered to most recent 3 months
- 310,808 records
- Text field: complaint narrative
- Target: product category

## Approach

### Data Preprocessing
- Removed records with missing labels
- Cleaned and normalized text
- Encoded target labels

### Models Implemented
1. Rule-Based Baseline  
2. TF-IDF + Support Vector Machine  
3. BERT (Transformer Model)  
4. Large Language Model (ChatGPT)

## Evaluation
- Accuracy
- Macro F1 Score
- Precision and Recall
- Confusion Matrix

## Results

| Model | Accuracy | Macro F1 |
|------|---------|----------|
| Baseline | 0.64 | 0.62 |
| SVM | 0.89 | 0.89 |
| BERT | 0.90 | 0.90 |
| LLM | 0.73 | 0.73 |

## Key Findings
- BERT achieved the highest performance
- SVM performed similarly to BERT
- LLM results varied across categories
- Baseline model overpredicted certain classes
- Some categories had overlapping language

## How to Run

1. Install dependencies

pip install pandas scikit-learn transformers datasets evaluate accelerate

2. Run Jupyter Notebook

jupyter notebook

3. Open and run

Keli_Duggar_Final_Project_Code.ipynb

## Future Improvements
- Hyperparameter tuning
- Improve class imbalance handling
- Fine-tune LLM models
- Add model explainability

## References
- Consumer Financial Protection Bureau
- AP News article on CFPB
