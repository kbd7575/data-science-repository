# Domestic Violence Risk Analysis

This notebook was created as a self-guided portfolio exercise. The dataset is sourced from Kaggle and contains information on domestic violence against women in a specific rural area of a developing country. The project objective is to investigate the correlation between socio-economic factors and the experience of domestic violence using exploratory analysis and classification models.

## Dataset Description

Each record includes:

- **Age**: Age of the respondent
- **Education**: Education level
- **Employment**: Employment status
- **Income**: Income level
- **Marital Status**: Marital status of the respondent
- **Violence**: Target variable indicating whether the respondent experienced domestic violence

## Exploratory Data Analysis

- **Demographics**: Majority of women are married (86%), with an average age of ~31. Most women have some education, and over 70% reported zero income.
- **Violence Distribution**:
  - Violence is distributed across all age groups.
  - Higher proportion of older women (>38) report violence.
  - Primary education is associated with the highest reported violence rate (34%).
  - Unemployed women show the highest proportion of violence (27%).

## Key Insights from EDA

- Violence is not isolated to one demographic but spans across all age and education groups.
- Education and income appear to influence risk levels, though correlation strength is weak.
- No strong linear relationships between categorical features and violence were found.

## Modeling Approach

### Preprocessing

- One-Hot Encoding was used for all categorical variables.
- Target variable (Violence) was converted to binary (target).
- Data was split into train/test using train_test_split with stratification to preserve class balance.
- Class imbalance was addressed using class_weight=balanced.

### Models Tested

- Decision Tree (used for interpretability)
- Feature importance was calculated using Random Forest.

### Decision Tree Interpretation

- Women over 45 with no education had the highest predicted risk (~81–84%).
- Women with income > $5,250 showed negligible predicted risk, regardless of other factors.

