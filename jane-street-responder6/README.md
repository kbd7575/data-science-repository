# Jane Street Real-Time Market Data Forecasting

**Goal:**  
Develop a machine learning model to predict responder_6 using a large, anonymized financial time-series dataset (47M+ rows) from a Kaggle competition hosted by Jane Street Group. The objective was to identify features with predictive power and model the behavior of a noisy target variable under real-world financial constraints.

---

## Tools & Technologies
- **Languages:** Python  
- **Libraries:** Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, Matplotlib, Seaborn  
- **ML Techniques:** Feature selection, normalization, cross-validation, ensemble models, PCA  
- **Environment:** Google Colab, local high-performance machine (Windows/Linux)

---

## Dataset Summary
- 47M rows, 92 anonymized features
- Target: `responder_6` — modeled as a regression problem
- Source: [Kaggle Competition](https://www.kaggle.com/competitions/jane-street-market-prediction)

---

## Project Highlights

### Feature Engineering & EDA
- Dropped irrelevant responders and high-missing-value features
- Used correlation and feature importance analysis to reduce features from 83 to 22
- Normalized using MinMaxScaler
- Plotted time-series patterns across anonymized time indices

### Modeling Approaches
| Method         | Notes                                                 | R² Score |
|----------------|--------------------------------------------------------|----------|
| **XGBoost**     | Best performance on curated sample                    | 0.0129   |
| LightGBM       | Full dataset overwhelmed model; better on subsets     | 0.015    |
| Random Forest  | Poor generalization; slow training on large data      | 0.0036   |
| PCA + Linear Regression | Applied dimensionality reduction                | Negligible |
| KNN / Decision Tree | Explored baseline classification & regression      | < 0.02   |

---

## Results & Insights
- No single model exceeded R² of 0.015 — consistent with leaderboard top scores
- Feature_06 and Feature_04 were most influential
- Even minor R² gains are significant in finance, where tiny predictive edges matter
- Demonstrated value of:
  - Downsampling for speed
  - Feature selection over raw volume
  - Cross-validation and careful tuning

---

## Key Takeaways
- Financial data is inherently noisy and difficult to predict
- Ensemble models with selective feature engineering outperformed deep models here
- Kaggle benchmark scores confirmed project challenges mirror real-world limitations

---

## Repository Structure
- Jane Street Real-Time Market Data Forecasting Notebook.ipynb: Preprocessing, EDA, model pipelines
- README.md: This file
---


