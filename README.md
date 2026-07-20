# Titanic-survival-prediction
 Predicting Titanic survival using Logistic Regression and Decision Trees, comparing model performance and overfitting behavior
# Titanic Survival Prediction — Logistic Regression & Decision Trees

A classification project predicting Titanic passenger survival, comparing Logistic Regression against Decision Trees (unlimited vs. depth-limited), built as a follow-up to Kaggle's Intro to Machine Learning course.

## Dataset
Titanic Dataset (via Kaggle, yasserh) — passenger details including class, sex, age, fare, and family aboard.

## Approach
- Handled missing values in `Age` (median imputation) and `Embarked` (mode imputation)
- Dropped `Cabin` (too many missing values), and non-predictive columns (`Name`, `Ticket`, `PassengerId`)
- One-hot encoded `Sex` and `Embarked`
- Trained and compared three models:
  - Logistic Regression (with feature scaling)
  - Decision Tree (unlimited depth)
  - Decision Tree (max_depth=4)

## Results

| Model | Accuracy |
|---|---|
| Logistic Regression | 79.4% |
| Decision Tree (unlimited) | 78.9% |
| Decision Tree (max_depth=4) | **82.1%** |

## Key Insight
Limiting the Decision Tree's depth improved accuracy from 78.9% to 82.1%, outperforming Logistic Regression — a direct, hands-on demonstration of overfitting: an unconstrained tree memorizes noise in training data, while controlled complexity generalizes better to unseen passengers.

Using scaled Logistic Regression coefficients, the strongest predictors of survival were `Sex` (being male sharply lowered survival odds) and `Pclass` (lower class tickets lowered survival odds) — consistent with the historical "women and children first" evacuation pattern and class-based access to lifeboats.

## What I Learned
- Full classification workflow: train/test split, fit, predict, evaluate
- Reading confusion matrices and classification reports (precision, recall, f1-score)
- Why feature scaling matters for fair coefficient comparison in Logistic Regression
- Overfitting vs. underfitting, demonstrated directly through tree depth tuning
