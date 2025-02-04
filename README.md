# Sales Call Success Prediction Model for GoTyme
A machine learning project to predict customer response to sales calls, developed as an independent validation model for the client's in-house data science team.

## Project Overview
This project develops a predictive model to help optimize sales call targeting by identifying customers most likely to respond positively to cold calls. The model uses customer demographics, telematics data, and macroeconomic indicators to predict sales success probability.

## Project Structure
flowchart TD
    A[Data Collection] --> B[Exploratory Data Analysis]
    B --> C[Feature Selection]
    C --> D[Feature Engineering]
    D --> E[Base Modeling]
    E --> F[Hyperparameter Tuning]
    F --> G[Model Interpretability]
    A --> G

## Pipeline Steps

### 1. Data Collection (`dataset.csv`)
- 35,000 observations with 20 features (10 numerical, 10 categorical)
- Binary response variable (1 = Yes, 0 = No)
- Features include customer demographics, telematics data, and macroeconomic indicators
- Pipe-delimited format

### 2. Exploratory Data Analysis (`EDA.ipynb`)
Key findings:
- Strong seasonal patterns in response rates (peaks ~45% in certain months)
- Previous campaign success is strongest predictor (~60% response rate)
- Employment type shows significant variation (10-30% response rates)
- Contact medium impacts success rates (15% vs 5%)
- Loan status has minimal impact on response rates

### 3. Feature Selection (`feature_selection.ipynb`)
Comprehensive feature importance analysis using multiple metrics:
- Mutual Information
- Random Forest importance
- Chi-square tests
- Point-biserial correlation
- Information Value (IV)

Key features identified:
- Call Duration (Feature_dn_1)
- Interest Rate (Feature_em_8)
- Previous Campaign Outcome (Feature_pd_19)
- Month Contacted (Feature_md_17)
- Consumer Price/Confidence Indices (Feature_cx_6/7)

### 4. Feature Engineering (`feature_engineering.ipynb`)
- Handling multicollinearity in economic indicators
- Categorical encoding optimization
- Feature scaling and transformation
- Removal of redundant features
- Export of processed dataset

### 5. Base Modeling (`base_modeling.ipynb`)
Model comparison with various sampling techniques:
- Logistic Regression
- Gradient Boosting
- Random Forest
- Decision Trees
- Gaussian Naive Bayes

Key findings:
- Original class distribution performed better than resampling
- TomekLinks showed minimal impact
- NearMiss significantly degraded performance
- Gradient Boosting and Logistic Regression emerged as top performers

### 6. Hyperparameter Tuning (`hyperparameter_tuning.ipynb`)
- Grid Search and Random Search optimization
- ROC and Precision-Recall curve analysis
- Optimal threshold determination (0.274)
- Performance metrics at threshold:
  - F1 score: 0.530
  - Precision: 0.508
  - Recall: 0.554

### 7. Model Interpretability (`interpretability.ipynb`)
Final model comparison:
- Gradient Boosting:
  - ROC AUC: 0.907
  - Better at identifying churners (4.1% true positive rate)
  - Longer training time (11.43s)
- Logistic Regression:
  - ROC AUC: 0.895
  - More interpretable
  - Faster training (0.49s)
  - Lower false positive rate

## Key Files
- `case_study.md`: Project requirements and context
- `dataset.csv`: Raw data file (pipe-delimited)
- `EDA.ipynb`: Exploratory data analysis notebook
- `feature_selection.ipynb`: Feature importance analysis
- `feature_engineering.ipynb`: Feature processing notebook
- `base_modeling.ipynb`: Initial model development
- `hyperparameter_tuning.ipynb`: Model optimization notebook
- `interpretability.ipynb`: Model interpretation notebook

## Requirements
- Python 3.12+
- Key libraries:
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - seaborn
  - imbalanced-learn
  - shap

## Results
The final model achieves:
- ROC AUC score of 0.907 (Gradient Boosting)
- Optimal classification threshold of 0.274
- Strong performance in identifying non-churners (86.6% true negative rate)
- Improved churner identification (4.1% true positive rate)
- Interpretable feature importance rankings

## Future Improvements
- Advanced model architectures (e.g., XGBoost, LightGBM)
- Real-time prediction capabilities
- Cost-benefit analysis integration
- Feature engineering for temporal patterns
- API deployment infrastructure

## Author
Pat Pascual
