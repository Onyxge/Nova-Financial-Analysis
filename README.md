# Nova Financial Solutions: Stock Sentiment and Volatility Analysis

## Executive Summary

**Objective:** Enhance predictive analytics capabilities by quantifying the relationship between financial news sentiment and stock market movements for six major tech companies: AAPL, AMZN, GOOG, META, MSFT, and NVDA.

**Methodology:** A data pipeline was developed to process 1.4 million news headlines from the FNSPID dataset. Timestamps were normalized to UTC, and Natural Language Processing tools (TextBlob) were used to compute sentiment scores. These scores were correlated against daily stock returns calculated using TA-Lib and PyNance.

**Key Findings:**
Daily aggregated sentiment shows a weak positive correlation with daily stock returns, averaging around 0.04. NVDA shows the strongest sensitivity. Daily sentiment is a lagging indicator.

---

## Installation and Environment Setup

This project requires Python 3.10 due to dependency constraints in PyNance and `distutils`. It also depends on the TA-Lib C library.

### macOS Setup

```
brew install python@3.10
brew install ta-lib
```

### Project Setup

```
git clone https://github.com/Onyxge/Nova-Financial-Analysis.git
cd <your-repo-name>
/usr/local/bin/python3.10 -m venv venv
source venv/bin/activate

export TA_INCLUDE_PATH="$(brew --prefix ta-lib)/include"
export TA_LIBRARY_PATH="$(brew --prefix ta-lib)/lib"
pip install -r requirements.txt
```

---

## Project Structure

```
├── .github/workflows/
├── data/
├── notebooks/
│   ├── 1_eda_descriptive_stats.ipynb
│   ├── 2_quantitative_analysis.ipynb
│   └── 3_sentiment_correlation.ipynb
├── screenshots/
├── src/
├── requirements.txt
└── README.md
```

---

## Final Report and Analysis

### Exploratory Data Analysis (EDA)

The dataset contains approximately 1.4 million financial news headlines. Headline length centers around 60 to 70 characters. News frequency peaks at US market open and close. Keywords such as Stocks, Earnings, and Estimates dominate.

### Technical and Quantitative Analysis

Indicators such as RSI, MACD, and moving averages were computed using TA-Lib. NVDA shows strong long term performance. Daily returns reflect volatility peaks during major market events.

### Correlation Analysis

Daily sentiment was merged with daily stock returns. Pearson correlation results show:

| Stock | Correlation | Interpretation  |
| ----- | ----------- | --------------- |
| NVDA  | 0.0482      | Weak positive   |
| AMZN  | 0.0415      | Weak positive   |
| AAPL  | 0.0388      | Weak positive   |
| MSFT  | 0.0321      | Not significant |
| GOOG  | 0.0295      | Not significant |

Daily sentiment has low predictive power at this timescale.

---

## Conclusion and Recommendations

Daily sentiment is absorbed quickly by markets. Minute level sentiment or event driven models are likely to produce better predictive value. NVDA shows the strongest sentiment sensitivity due to speculative AI sector interest.

---

