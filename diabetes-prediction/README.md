# Diabetes Risk Prediction

## 📌 Project Overview
This project aims to build a predictive model that identifies individuals at risk for diabetes using health and lifestyle data. The dataset, derived from the CDC’s Behavioral Risk Factor Surveillance System (BRFSS), was used to train multiple machine learning models with a focus on recall—minimizing false negatives in a critical healthcare context.

---

## 🧰 Tools & Technologies
- Python (Pandas, NumPy, Scikit-learn)
- Decision Tree, Random Forest
- SMOTETomek, ADASYN (resampling)
- PCA (dimensionality reduction)
- ROC-AUC, Confusion Matrix, Recall-focused metrics

---

## 📊 Dataset Summary
- Source: CDC BRFSS via UCI Machine Learning Repository
- Size: 253,680 rows × 21 features
- Target: `diabetes_012` (0 = healthy, 1 = pre-diabetes, 2 = diabetes)

---

## 🧪 Modeling Approach

| Model      | Description                                           | Key Performance Metric |
|------------|-------------------------------------------------------|-------------------------|
| **Model 1** | Balanced binary classes (0 vs 1)                      | Random Forest recall: 80% |
| **Model 2** | Imbalanced multi-class (0, 1, 2), no adjustments      | Accuracy high, recall poor for class 2 |
| **Model 3** | Imbalanced multi-class with SMOTETomek + PCA         | Class 2 recall: 72% (Random Forest) |

### Key Steps:
- EDA to assess feature importance (BMI, GenHlth, HighBP most predictive)
- Handled class imbalance using SMOTETomek & ADASYN
- PCA applied to reduce feature space and mitigate overfitting
- Final model: Random Forest on balanced dataset with optimized hyperparameters

---

## ✅ Results

| Model     | Accuracy | Class 2 Recall | Notes |
|-----------|----------|----------------|-------|
| Decision Tree (M1) | 71% | 76% | Simpler model, fair recall |
| Random Forest (M1) | 75% | 80% | Best balance of accuracy and recall |
| Random Forest (M3) | 69% | 72% | Best performance on imbalanced multi-class |

> In a healthcare setting, minimizing false negatives is critical—especially in identifying undiagnosed diabetes.

---

## 💡 Key Insights
- A false negative (missed diabetes case) is more harmful than a false positive.
- Class imbalance dramatically affects multi-class model performance.
- SMOTE + PCA significantly improved recall for minority class (diabetes = 2).
- Healthcare-focused models must balance accuracy with ethical cost of misclassification.

---

## 📂 Files
- `notebooks/` — Full modeling and evaluation code
- `data/` — Public UCI dataset (or a sample)
- `README.md` — Project overview

---

## 🔍 Future Work
- Explore neural networks for deeper interaction modeling
- Add socioeconomic and geographic data for disparity analysis
- Deploy a lightweight API model for front-line medical screening tools

---

📌 _This project showcases practical healthcare data science, including stakeholder-driven metric prioritization, imbalanced classification strategies, and real-world ML trade-offs._


