## Overview
A complete ML pipeline predicting which telecom customers will churn next month,
enabling the retention team to intervene proactively. The dataset contains 7,043 
customers with 20 features including contract type, tenure, monthly charges, and 
internet service type. Six engineered features are added before modelling.

## Engineered Features
- ChargesPerMonth: average monthly spend (TotalCharges / Tenure)
- ServiceCount: number of active add-on services (0–8)
- TenureGroup: binned into New / Growing / Loyal / Champion
- HighValueCustomer: monthly charges above 75th percentile
- ContractRiskScore: risk encoding of contract type (1–3)
- ChargesRatio: monthly / total charges ratio

## Model Results
| Model | AUC-ROC | AUC-PR | F1 | Recall |
|---|---|---|---|---|
| Voting Ensemble | ~0.85 | ~0.64 | ~0.60 | ~0.75 |
| Gradient Boosting | ~0.84 | ~0.62 | ~0.59 | ~0.73 |
| Random Forest | ~0.83 | ~0.61 | ~0.58 | ~0.72 |
| Logistic Regression | ~0.79 | ~0.54 | ~0.54 | ~0.68 |

## Business Recommendations
- Month-to-month customers have 3x higher churn — offer contract upgrade discounts
- Fibre optic customers churn more — review pricing competitiveness
- New customers (0–12 months) churn most — launch 90-day onboarding programme
- Adding Tech Support reduces churn significantly — offer free for 3 months

  Tech Stack
  | Category      | Tool                       | Purpose                                          |
| ------------- | -------------------------- | ------------------------------------------------ |
| Language      | Python 3.10+               | All code                                         |
| ML Framework  | Scikit-learn 1.3+          | All models, pipelines, cross-validation, metrics |
| Model         | LogisticRegression         | Linear baseline classifier                       |
| Model         | RandomForestClassifier     | Tree ensemble with feature importance            |
| Model         | GradientBoostingClassifier | Boosted trees for high accuracy                  |
| Model         | XGBClassifier (XGBoost)    | Optimized gradient boosting                      |
| Model         | VotingClassifier           | Soft-voting ensemble of all models               |
| Preprocessing | RobustScaler               | Scaling robust to outliers                       |
| Data          | Pandas / NumPy             | Loading and feature engineering                  |
| Serialization | Joblib                     | Saving trained model pipelines to disk           |
| Visualization | Matplotlib / Seaborn       | ROC curves, confusion matrices, plots            |
| Testing       | Pytest                     | Unit tests for pipeline modules                  |
| Config        | PyYAML                     | Project configuration settings                   |
| Notebook      | Jupyter Lab                | Interactive analysis notebook                    |
