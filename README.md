# Heart Disease Prediction Model

A logistic regression model that predicts the presence of heart disease from clinical
indicators, built on the UCI Cleveland Heart Disease dataset. This project also includes an
interactive QA chatbot (powered by BioBERT) that lets users query the dataset directly.

## Project Overview
This project uses statistical modeling to identify which clinical factors are most
associated with heart disease presence, and to what degree. Rather than treating the model
as a black box, the focus is on interpreting the model's coefficients, odds ratios, and
probability thresholds to understand *why* the model predicts what it does — not just how
accurate it is.

## Dataset
- **Source:** UCI Machine Learning Repository — Cleveland Heart Disease dataset (via `ucimlrepo`)
- **Target variable:** Presence/absence of heart disease
- **Features:** Clinical indicators such as age, cholesterol, resting blood pressure, and other
  diagnostic measurements

## Methodology
1. **Data cleaning & preprocessing** — converted categorical codes into usable formats and
   prepared structured training/testing splits
2. **Model building** — trained a logistic regression model (Python, `statsmodels`) to predict
   heart disease presence from clinical indicators
3. **Interpretation** — computed and interpreted odds ratios, log-odds, and probability
   thresholds to quantify risk factors and assess model fit
4. **Interactive QA layer** — built a HuggingFace BioBERT-powered chatbot that allows users to
   query the dataset and model results through a simple interactive interface

## Key Results
- Logistic regression model achieved 83.5% training accuracy / 80% test accuracy, with training AUC of 0.933 and test AUC of 0.817
- Strongest predictors of heart disease presence: reversible thallium defect (OR ≈ 6.97), number of major vessels affected (OR ≈ 5.64), and sex (OR ≈ 2.77)
- Full clinical model substantially outperformed an age-only baseline (AUC 0.817 vs. 0.733 on test data)
- Built a BioBERT-powered QA chatbot to answer cardiology questions using custom clinical context

## Files
- `heart_disease_project.ipynb` — full analysis: data cleaning, model training, evaluation,
  and BioBERT chatbot implementation
- `processed_cleveland.csv` — cleaned dataset used for modeling

## Tools and Libraries
Python, Pandas, Statsmodels, HuggingFace Transformers (BioBERT)
