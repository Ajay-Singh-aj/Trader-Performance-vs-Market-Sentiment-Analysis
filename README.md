# Trader Performance vs Market Sentiment

##  Project Overview
This project analyzes the relationship between Bitcoin market sentiment (Fear/Greed Index) and trader behavior and performance on the Hyperliquid exchange.

The goal is to understand whether trader profitability and activity change across sentiment regimes and to derive actionable trading insights.

The analysis includes:
- Data cleaning and alignment of sentiment and trading datasets
- Feature engineering of daily trader performance metrics
- Behavioral analysis across sentiment conditions
- Trader segmentation and clustering
- A simple predictive model for next-day trader profitability

---

##  Dataset Description

### 1. Bitcoin Fear & Greed Index
Contains daily market sentiment classifications.

**Columns include:**
- `date` – calendar date
- `classification` – Fear / Extreme Fear / Neutral / Greed / Extreme Greed
- `value` – sentiment index score

---

### 2. Hyperliquid Trader History
Contains individual trade-level execution data.

**Important fields used:**
- `Account` – trader identifier
- `Timestamp IST` – execution timestamp
- `Closed PnL` – realized profit/loss per trade
- `Size USD` – trade size
- `Side` – buy/sell direction

---

##  Methodology

### Data Preparation
- Converted timestamps to datetime format
- Aggregated trade-level data into **daily trader metrics**
- Created features including:
  - Daily PnL per trader
  - Trade frequency per day
  - Average trade size
  - Win rate
  - Long/short ratio
- Merged trader metrics with daily sentiment classification

---

### Analysis Performed
1. **Performance vs Sentiment**
   - Compared profitability and win rates across sentiment regimes
   - Visualized PnL distributions

2. **Behavior vs Sentiment**
   - Analyzed trading frequency, size, and positioning bias
   - Identified behavioral shifts during Fear vs Greed periods

3. **Trader Segmentation**
   - Segmented traders into:
     - High vs Low activity
     - Consistent vs Inconsistent profitability

4. **Clustering (Bonus)**
   - Applied KMeans clustering to identify behavioral archetypes
   - Features included activity, profitability, win rate, trade size, and volatility

5. **Predictive Modeling (Bonus)**
   - Built a Random Forest model predicting **next-day profitability**
   - Used sentiment + behavioral lag/rolling features
   - Applied time-based train/test split to avoid data leakage

---

##  Key Insights

- Trader profitability varies across sentiment regimes.
- Trading activity and position sizes increase during fearful markets.
- High trading frequency does not necessarily lead to higher profitability.
- Distinct trader archetypes exist, suggesting different trading styles and risk profiles.
- Sentiment and trader behavior contain predictive signals for short-term outcomes.

---

##  Strategy Implications

- Fear regimes may offer trading opportunities but require stricter risk management.
- Greed regimes tend to produce more consistent outcomes, favoring systematic strategies.
- Segment-specific strategies may outperform one-size-fits-all approaches.

---

##  How to Run

### 1. Install dependencies
```bash
pip install pandas numpy matplotlib scikit-learn jupyter
