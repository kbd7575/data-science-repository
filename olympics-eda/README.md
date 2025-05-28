# Olympics Data Analysis (1896–2024)

This project analyzes historical trends and patterns in the Olympic Games from 1896 through 2024, with a particular focus on the 2020 Tokyo and 2024 Paris Summer Games.

## 🔍 Objectives

- Analyze medal distributions by country and sport
- Explore gender participation trends over time
- Identify dominant countries in specific sports
- Predict medal outcomes using classification models
- Examine sentiment and tweet trends during the Olympics

## 📊 Tools & Technologies

- Python (Pandas, Matplotlib, Seaborn, Scikit-learn)
- Decision Tree Classifier
- Kaggle datasets
- Natural Language Processing (NLP): Sentiment analysis, Word Cloud

## 📁 Data Sources

- [Summer Olympics Medals 1896–2024](https://www.kaggle.com/datasets/stefanydeoliveira/summer-olympics-medals-1896-2024)
- Custom CSV/Excel files for medal counts, athletes, and Twitter sentiment

## 🧠 Key Insights

- USA and China consistently dominate medal counts
- Gender parity is increasing, though some sports remain skewed
- Decision Tree model (max_depth=3) predicted medal class with 87% accuracy
- Social media sentiment during 2020 Olympics was largely positive

## 🤖 ML Model Performance

- Accuracy: 87%
- Most accurate for predicting silver medalists
- Class Imbalance addressed with pruning techniques

## 📌 Contributors

Kéli Davis  
Maybel Herrera  
Sandy Leung

## 📎 Files in This Repo

- `data/` - Contains datasets used
- `notebooks/` - Jupyter notebooks for EDA and modeling
- `visuals/` - All static plots and word clouds
- `README.md` - You’re here!


