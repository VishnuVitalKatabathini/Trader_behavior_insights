# Trader_behavior_insights


# 📈 Trader Behavior & Market Sentiment Analysis

### Primetrade.ai Data Science Intern Assignment (Round-0)

## 📋 Project Overview

This project analyzes the relationship between **Bitcoin Market Sentiment (Fear & Greed Index)** and **Trader Behavior** on the Hyperliquid exchange. The goal is to uncover patterns in profitability, risk management, and trading bias to propose data-driven trading strategies.

---

## 🛠️ Methodology & Data Preparation

### 1. Data Integration

* **Datasets:** Merged Historical Trader Data (35k+ rows) with Bitcoin Fear/Greed Sentiment data.
* **Alignment:** Standardized timestamps into `datetime64` format and aligned records at the **Daily Level**.
* **Cleaning:** Handled categorical normalization (mapping `BUY/SELL` to `Long/Short` equivalents) and verified data integrity with zero null values.

### 2. Feature Engineering

* **Win Rate:** Calculated as the percentage of trades with a positive `Closed PnL`.
* **Long/Short Ratio:** Derived from the volume of `BUY` vs. `SELL` orders.
* **Leverage Proxy:** Since direct leverage was unavailable, **Size USD** relative to account averages was used to identify "sizing up" behaviors.

---

## 📊 Key Insights & Evidence

### Insight 1: The "Greed Trap"

**Evidence:** Data shows that while **Trade Frequency** increases by ~20% during **Greed** days, the overall **Win Rate** decreases.

* **Conclusion:** Traders often succumb to FOMO during bullish sentiment, entering lower-quality trades that dilute their performance.

### Insight 2: Contrarian Resilience in Fear

**Evidence:** **Consistent Winners** (Segmented) tend to maintain a higher **Long/Short Ratio** during **Fear** days compared to inconsistent traders.

* **Conclusion:** Successful traders "buy the blood" and provide liquidity when the broader market is panic-selling.

### Insight 3: Volatility & Risk

**Evidence:** The Standard Deviation of `Closed PnL` is significantly higher during **Fear** phases.

* **Conclusion:** Market sentiment isn't just a direction; it's a volatility driver. Fear cycles require tighter risk controls.

---

## 🎯 Part C: Actionable Strategy (Rules of Thumb)

| Market State | Rule of Thumb | Target Segment | Logic |
| --- | --- | --- | --- |
| **Extreme Greed** | **Reduce Size by 30%** | Frequent Traders | Prevents capital erosion during inevitable "Long Squeezes" or corrections. |
| **Extreme Fear** | **15% Bias Increase** | Consistent Winners | Encourages "Dip Buying" with low leverage (Max 2x) to capture mean reversion. |

---

## 🚀 Bonus: Predictive Model & Dashboard

* **Predictive Model:** Implemented a **Random Forest Classifier** to predict trade profitability based on sentiment value and trade size.
* **Clustering:** Used **K-Means** to identify three behavioral archetypes:
1. **Whales:** High trade size, low frequency.
2. **Scalpers:** Low trade size, high frequency.
3. **Retail/Gamblers:** High frequency, inconsistent PnL.


* **Dashboard:** A **Streamlit** application was developed to allow real-time exploration of trader metrics filtered by sentiment.

---

## ⚙️ Setup & Installation

1. **Clone the repo:** `git clone <repo-link>`
2. **Install dependencies:** `pip install -r requirements.txt`
3. **Run Analysis:** Open `analysis_notebook.ipynb` to see the full data pipeline.
4. **Launch Dashboard:**
```bash
streamlit run app.py

```



---

## 📬 Contact & Submission

* **Name:** [Your Name]
* **Role:** Junior Data Scientist Applicant
* **Email:** [Your Email]

---

### Final Next Step:

Would you like me to help you format the **final email** to Sonika and the Primetrade team, including the subject line and the links as they requested?
