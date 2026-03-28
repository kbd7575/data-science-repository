# Consumer Complaint Classification with Text Mining

Author: Keli Duggar  
Course: IST 736 – Text Mining  
Institution: Syracuse University  

---

## Project Overview

This project evaluates how different text mining techniques perform in classifying consumer financial complaints. Using data from the Consumer Financial Protection Bureau (CFPB), the goal is to predict the product category of a complaint based on its narrative text.

---

## Objectives

- Build a multi-class classification system for complaint narratives  
- Compare multiple modeling approaches  
- Evaluate performance using robust metrics  

---

## Dataset

- Source: CFPB Consumer Complaint Database  
- Timeframe: Most recent 3 months  
- Size: 310,808 rows and 18 columns  

Key fields:
- clean_text: complaint narrative  
- product_short: product category (target)  

Notes:
- Only complaints with narratives were used  
- Missing labels were removed  

---

## Methodology

1. Rule-Based Model (Baseline)  
   - Keyword-based classification  

2. TF-IDF + Support Vector Machine  
   - Text vectorization with TF-IDF  
   - Linear SVM classifier  

3. BERT  
   - Transformer-based classification  
   - Context-aware embeddings  

4. Large Language Model (ChatGPT)  
   - Zero-shot or few-shot classification  

---

## Evaluation Metrics

- Accuracy  
- Macro F1 Score  
- Precision and Recall  
- Confusion Matrix  

---

## Results Summary

Model        | Accuracy | Macro F1  
-------------|----------|----------  
Baseline     | 0.64     | 0.62  
SVM          | 0.89     | 0.89  
BERT         | 0.90     | 0.90  
LLM          | 0.73     | 0.73  

---

## Key Findings

- BERT achieved the highest performance  
- SVM performed nearly as well as BERT  
- LLM results were inconsistent across categories  
- Baseline model overpredicted certain classes  

---

## Generalization

- Baseline: Poor generalization  
- SVM: Good within financial domain  
- BERT: Good within financial domain  
- LLM: Moderate cross-domain adaptability  

---

## Ethical Considerations

- Data is anonymized but may contain sensitive financial content  
- Used only for academic purposes  
- Models should not be used to unfairly prioritize complaints  

---

## Repository Structure

data/                  Processed dataset  
notebooks/             Jupyter notebooks  
report/                Final project report  
README.md              Project documentation  

---

## How to Run

1. Clone the repository  
2. Install dependencies  

pip install pandas scikit-learn transformers datasets  

3. Run the notebook  

jupyter notebook  

4. Execute the main notebook file  

---

## References

Consumer Financial Protection Bureau. Twelve Years of Protecting Consumers and Honest Businesses.  

Boak, Josh. Trump Administration Orders Consumer Protection Bureau to Stop Some Work. AP News, 2025.  

---

## Future Improvements

- Hyperparameter tuning  
- Improved handling of class imbalance  
- Fine-tuning LLM models  
- Model explainability methods  
