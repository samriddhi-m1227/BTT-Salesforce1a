# 📊 Stock Price Prediction from Financial News  

---

**Challenge Advisor:** *Atena Sadeghi*  

**AI Studio Coach:** *Leah Dsouza*

**Program:** *Break Through Tech AI Studio*

**Host Company:** *Salesforce*

---

## 🎯 **Project Highlights**

- Built an end-to-end ML pipeline combining financial news sentiment and historical stock data.
- Applied FinBERT (LLM) to extract daily sentiment signals from news headlines.
- Evaluated multiple models (Lasso, Random Forest, XGBoost), selecting XGBoost as the final model.
- Used SHAP to interpret model behavior and assess the real impact of news features.
- Delivered insights on the limitations of sentiment-based prediction for short-term market forecasting.

---

## 🏗️ **Project Overview**

This project explores the intersection of **financial news and market prediction**, aiming to forecast **short-term stock price movements** using machine **learning and large language models (LLMs)**.

Developed as part of the **Break Through Tech AI Studio** in collaboration with **Salesforce**, our goal was to investigate whether **public news sentiment**, when combined with historical market data, can improve predictions of the **next-day opening price of the S&P 500**.

---

## 💼 **Business Question**

Can financial news sentiment combined with historical market data improve the accuracy of short-term stock price predictions?

---

## 📈 Business Impact

- Supports investment and risk management decisions
- Improves understanding of how public perception impacts market value
- Demonstrates a scalable framework applicable to other sectors influenced by news

---

## 👩🏽‍💻 **Setup and Installation**

### Repository Structure
```bash
├── archive/ # Kaggle Data
│   ├── cnbc_headlines.csv
│   ├── guardian_headlines.csv
│   └── reuters_headlines.csv
├── notebooks/
│   ├── Salesforce1A_Data.ipynb # Data EDA & Analysis
│   └── Salesforce1A_Model.ipynb # Model
├── docs/
│   ├── Salesforce1A_AI Studio Final Presentation_Fall 2025 AI Studio.pptx # Presentation slides
├── requirements.txt
└── README.md
```

---

## ℹ️ Steps to Run the Project

1. **Clone the repository**
```bash
git clone https://github.com/your-repo-name.git
cd your-repo-name
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Access the datasets**

- Financial News Headlines (Kaggle): https://www.kaggle.com/datasets/notlucasp/financial-news-headlines
- Historical stock data retrieved using yfinance: https://github.com/ranaroussi/yfinance

4. Run the notebooks
- Start with exploratory data analysis notebooks
- Proceed to feature engineering and model training notebooks

---

## 📊 Data Exploration

### Data Sources

Market Data
- Source: Yahoo Finance (yfinance)
- Target: S&P 500
- Features: Open, High, Low, Close, Volume, rolling averages, volatility

Financial News
- Source: Kaggle Financial News Headlines dataset
- Providers: CNBC, Guardian, Reuters
- NLP Model: FinBERT 

### Feature Engineering

- Daily sentiment probabilities (positive, negative, neutral)
- Number of headlines per day
- Strong sentiment indicators
- Lagged price features and rolling averages

### Key EDA Insights

- S&P 500 provides a stable modeling target
- Price features show strong autocorrelation
- News sentiment signals are weak when averaged daily

(EDA visualizations such as sentiment distributions and price trends are included in the notebooks.)

---

## 🧠 Model Development

### Models Tested

1. Lasso Regression
2. Random Forest
3. XGBoost (Final Model)

### Final Model: XGBoost

- Captures nonlinear price dynamics
- Performs best overall among tested models
- Tuned using time-series cross-validation
- Interpreted using SHAP values

---

## 📈 Results & Key Findings

### Performance Summary

- Lasso: Lowest RMSE and MAE, highest R²
- XGBoost: Strong performance, second-best overall
- Random Forest: Underperformed during volatile periods

### SHAP Insights

- Predictions rely heavily on recent price history (Close, High, rolling averages)
- News sentiment features contribute minimally
- Confirms risk of data leakage when predicting next-day open using same-day close

---

## 🧪 Discussion & Reflection

### What Worked
- Robust preprocessing and feature engineering
- Strong baseline models for comparison
- Clear interpretability using SHAP

### What Didn’t
- News sentiment alone is not a strong short-term signal
- Daily averaging of headlines dilutes meaningful events
- Potential leakage inflates performance metrics

---

## 🚀 Next Steps

- Address data leakage by redesigning prediction targets
- Explore event-based NLP features instead of sentiment averages
- Use embeddings or topic modeling for richer news representations
- Investigate hybrid architectures separating price and news modeling

---

## 🛠️ Tech Stack

- Languages: Python
- ML & NLP: Scikit-learn, XGBoost, Transformers, FinBERT
- Data: Pandas, NumPy, yfinance
- Visualization: Matplotlib, Seaborn
- Explainability: SHAP
- Environment: Google Colab, VS Code


