# Manufacturing Defect Classification

This project builds a classification model to predict defect status in a manufacturing environment using structured production data. The goal is to identify defective materials before they move downstream in the supply chain, reducing waste and improving product quality.

---

## Dataset Overview

- Source: Kaggle (Manufacturing Defect Dataset)
- Records: 3,240 production batches
- Target Variable: `DefectStatus` (0 = Non-defective, 1 = Defective)

### Features include:

- **Production Metrics:** ProductionVolume, ProductionCost, DefectRate
- **Quality Indicators:** SupplierQuality, QualityScore, MaintenanceHours
- **Logistics & Operations:** DeliveryDelay, DowntimePercentage, InventoryTurnover, EnergyConsumption
- **Workforce & Safety:** WorkerProductivity, SafetyIncidents
- **Additive Manufacturing:** AdditiveProcessTime, AdditiveMaterialCost

---

## Project Structure

### 1. Data Exploration
- Histogram and boxplot visualizations
- No missing values detected
- Low outlier impact
- Imbalance in `DefectStatus` observed

### 2. Baseline Modeling
- Scaled all features using StandardScaler
- Models evaluated: Logistic Regression, Random Forest, LightGBM
- Evaluation Metrics: Accuracy, Precision, Recall, F1 Score, ROC AUC
- Target imbalance handled with class_weight='balanced' for appropriate models

### 3. Feature Engineering
- Log transformation: log(ProductionVolume)
- Interaction terms: Production x DefectRate, Defect per Quality, Defect per Maintenance
- Categorical binning: MaintenanceHours binned into Low, Medium, High and one-hot encoded
- Dropped redundant features: raw DefectRate, ProductionVolume, and MaintenanceHours

### 4. Re-Modeling with Engineered Features
- Re-trained all models using engineered features
- Assessed improvements in model performance

### 5. Hyperparameter Tuning
- Performed GridSearchCV for:
  - Logistic Regression (C, penalty)
  - Random Forest (n_estimators, depth, split criteria)
  - LightGBM (leaves, depth, learning rate)

### 6. Cross-Validation
- Applied Stratified 5-Fold Cross Validation
- Evaluated model robustness using mean ROC AUC and standard deviation

---

## Final Evaluation

- Cross-validation confirms models are stable with low variance
- **LightGBM** performed best with highest ROC AUC and stability
- Feature engineering did not improve model performance
- **Baseline LightGBM** is recommended as the final model due to:
  - Highest ROC AUC (0.954)
  - Balanced precision and recall (minimizes false negatives)
  - Simplicity (no additional complexity from engineered features)

---

## Key Takeaways

- Tree-based models like LightGBM can capture nonlinear feature interactions natively.
- In manufacturing defect classification, recall is critical to avoid releasing faulty products.
- Simpler models using raw features may be just as effective when data quality is high and features are informative.

---

## Requirements

- Libraries:
  - pandas, numpy, matplotlib, seaborn
  - scikit-learn
  - lightgbm
