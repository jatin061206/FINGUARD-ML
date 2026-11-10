# FinGuard - ML: AI-Powered Fraud Detection System 

"Real-Time Financial Anomaly Detection using Machine Learning & Explainable AI!"

## Project Overview

**FinGuard-ML** is an AI-powered fraud detection system designed to identify suspicious financial transactions in real time.
The project replicates a real-world financial risk pipeline — from raw data ingestion to machine learning modeling, interpretability, and interactive visualization.

With the increasing volume of digital payments and online transactions, fraud detection has become one of the most critical challenges in the financial industry. FinGuard leverages machine learning and explainable AI to detect unusual behavior patterns that may indicate fraud, thus helping institutions reduce financial losses, enhance compliance, and increase trust.

## Problem Statement 

In modern finance, millions of transactions happen every minute. Traditional rule-based systems struggle to detect emerging and subtle fraud patterns — leading to:

- Missed fraudulent transactions (false negatives)
- Unnecessary alerts for legitimate users (false positives)
- Financial losses, compliance risks, and poor customer experience

FinGuard-ML solves this by applying machine learning models that learn from transaction patterns and automatically flag anomalies — while explaining why each transaction is considered suspicious.

## Project Objectives 

- Detect fraudulent transactions using supervised and unsupervised ML methods.
- Build an end-to-end, production-style pipeline (data → model → dashboard).
- Integrate Explainable AI (XAI) using SHAP to make the system transparent.
- Create an interactive Streamlit dashboard for analysts to visualize and act on fraud alerts.
- Provide a modular and scalable codebase ready for integration into financial systems.

## Tech Stack 

| Category | Tools & LIbraries |
| -------- | ----------------- |
| Programming Language | Python |
| Data Analysis | Pandas, Numpy |
| Data Visualization | matplotlib, seaborn and plotly |
| Modeling | Scikit-learn, XGBoost, LightGBM, PyCaret |
| Explainability | SHAP, LIME |
| Deployment | Streamlit Cloud |
| Database | PostgreSQL |
| Version Control | Git + GitHub |

## Project Structure 

```markdown
FinGuard-ML/
│
├── data/
│   ├── raw/                     # Original dataset (creditcard.csv)
│   └── clean_data.csv           # Cleaned and processed data
│
├── notebooks/
│   ├── 01_data_exploration.ipynb        # Data loading & basic exploration
│   ├── 02_eda_and_cleaning.ipynb        # EDA and preprocessing
│   ├── 03_feature_engineering.ipynb     # Sampling, scaling, splitting
│   ├── 04_model_training.ipynb          # ML model training & evaluation
│   ├── 05_model_explainability.ipynb    # SHAP & LIME explanations
│
├── models/
│   └── best_model.pkl                  # Saved trained model
│
├── src/
│   ├── data_preprocessing.py           # Data cleaning & preparation functions
│   ├── model_training.py               # Functions to train & evaluate models
│   ├── model_explainability.py         # SHAP & LIME visualizations
│   └── utils.py                        # Helper functions (metrics, logging)
│
├── dashboard/
│   └── app.py                          # Streamlit dashboard for fraud detection
│
├── requirements.txt                    # Python dependencies
├── README.md                           # Project overview and documentation
└── LICENSE                             # Open-source license (MIT recommended)
```

## Workflow Methodology 

1. **Data Collection & Understanding**

Dataset: [Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) – Kaggle

- 284,807 transactions
- Only 492 fraud cases (~0.17%) → highly imbalanced

2. **Exploratory Data Analysis (EDA)**

- Distribution of legitimate vs fraudulent transactions
- Time and amount distribution
- Feature correlations and anomaly patterns

3. **Feature Engineering & Sampling**

- Applied scaling (StandardScaler)
- Addressed imbalance using SMOTE (Synthetic Minority Oversampling)
- Split data set into 80% training, 20% testing

4. **Model Building & Evaluation**

Models evaluated:

- Logistic Regression (Baseline)
- Random Forest
- XGBoost
- LightGBM

Metrics used:

- Precision, Recall, F1-score
- ROC-AUC
- Confusion Matrix

Best model saved using joblib.dump(model, 'models/best_model.pkl')

5. **Explainability with SHAP**

- SHAP values identify which features contribute most to fraud prediction
- Analysts can understand why a transaction is flagged
- Improves trust and regulatory compliance

6. **Interactive Streamlit Dashboard**

Key features:

- Upload transaction CSV file
- Predict fraud probability for each transaction
- Visualize top risky transactions

SHAP summary plots for explainability

7. Deployment

Deployed publicly via Streamlit Cloud: *Include the link later!*

**Real-World Impact** 
| Problem | FinGuard Solution | Impact |
| ----- | --------- | ------- |
| Fraudulent payments going unnoticed | Machine Learning models detect anomalises | Reduced financial losses |
| Lack of transparency in AI decisions | SHAP explanations show feature importance | Regulatory compliance |
| Overwhelming manual reviews | Automated alerts and dashboards| Faster fraud response |
| Poor scalability of rule-based systems | Adaptive learning algorimthms | Continuous improvement |

## Example Outputs
- Confusion Matrix showing true vs predicted fraud cases
- ROC Curve illustrating model performance
- SHAP Summary Plot explaining top contributing features
- Interactive Dashboard displaying suspicious transaction flags

## Run this project locally 
```bash
# 1. Clone the repository
git clone https://github.com/Bestine/FinGuard-ML.git
cd FinGuard-ML

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the Streamlit dashboard
streamlit run dashboard/app/py
```

## Future Enhancements 

| Enhancement                 | Description                                                                                           |
| --------------------------- | ----------------------------------------------------------------------------------------------------- |
| **LLM Integration (GenAI)** | Add an LLM-powered fraud explainer (e.g., “Why was this transaction flagged?”) using OpenAI or Ollama |
| **FastAPI Backend**         | Create REST API for external systems to query predictions                                             |
| **Alerting System**         | Send automated email/SMS alerts for high-risk transactions                                            |
| **Database Integration**    | Connect with PostgreSQL for storing transactions and logs                                             |
| **Real-Time Inference**     | Integrate Kafka or Celery for live fraud monitoring                                                   |
| **UI Expansion**            | Add role-based access (analyst, admin) and visualization filters                                      |


