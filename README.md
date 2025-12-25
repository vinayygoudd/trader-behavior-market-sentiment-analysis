# Trader Behavior & Risk Analysis by Market Sentiment (Bitcoin)

## 📌 Overview
This project analyzes how **Bitcoin market sentiment (Fear vs Greed)** influences **trader behavior, risk-taking, and performance** using historical execution-level trading data combined with the Fear & Greed Index.

The objective is not to predict price direction, but to understand **how sentiment affects trader risk behavior**, position sizing, and downside exposure—insights that are directly applicable to trading risk management and trader evaluation.

---

##  Problem Statement
Does market sentiment change:
- How often traders win?
- How much risk they take?
- How severe their losses are?

If win rates remain similar across sentiment regimes, **what actually differentiates trader outcomes during Fear vs Greed markets?**

---

##  Tools & Technologies
- **Python** (Pandas, NumPy, Matplotlib, Seaborn) – data cleaning & analysis  
- **Power BI** – KPI creation & interactive dashboard  
- **Google Colab** – analysis environment  

---

## 📂 Dataset Description
### 1. Fear & Greed Index (Daily)
- Date
- Sentiment classification (Fear, Extreme Fear, Neutral, Greed, Extreme Greed)

### 2. Historical Trader Data
- Account
- Execution price
- Trade size (USD & tokens)
- Side (Buy/Sell)
- Closed PnL
- Timestamp
- Fees and trade metadata

Sentiment categories were **simplified into two regimes**:
- **Fear** (Fear + Extreme Fear)
- **Greed** (Greed + Extreme Greed + Neutral)

---

##  Methodology
1. **Data Cleaning & Standardization**
   - Standardized column naming
   - Converted timestamps to proper datetime formats
   - Removed incomplete trade records

2. **Sentiment Mapping**
   - Mapped each trade to the corresponding daily sentiment regime
   - Inner join ensured only valid sentiment-mapped trades were analyzed

3. **Feature Engineering**
   - `is_profitable`: win/loss indicator
   - `abs_pnl`: absolute loss magnitude
   - `high_exposure`: top 25% trade sizes as a risk proxy

4. **Analysis Focus**
   - Win rate comparison
   - Average vs total PnL
   - Position sizing behavior
   - Loss severity and downside risk

---

##  Dashboard (Power BI)
The Power BI dashboard presents:
- **KPIs**
  - Total Trades Analyzed
  - Overall Win Rate
  - Average Trade Size
  - Profit Factor
- **Charts**
  - Trade distribution by sentiment
  - Total Profit/Loss by sentiment
  - Win rate by sentiment
  - Risk exposure (avg trade size)
  - Loss severity comparison

The dashboard is designed as a **one-page executive view**, emphasizing clarity, consistency, and decision-ready insights.

---

## Key Findings
1. **Win rates are nearly identical across Fear and Greed**
   - Sentiment does not materially change trader accuracy.

2. **Fear markets exhibit significantly higher risk-taking**
   - Larger average trade sizes.
   - Wider PnL distributions.
   - Higher loss severity.

3. **Greed markets show more controlled position sizing**
   - Tighter distributions, but occasional extreme losses.

4. **Risk distribution—not win rate—is the main differentiator**
   - Downside exposure and volatility explain performance differences more than success rate.

---

## Strategy Implications
- Risk limits should be **tightened during Fear regimes**.
- Position sizing should adapt dynamically to sentiment conditions.
- **Loss severity and drawdown metrics** are more informative than win rate alone.
- Trader evaluation should emphasize **consistency across sentiment regimes**.
- Market sentiment is better suited for **risk management frameworks** than directional trading signals.

---

## Limitations
- Sentiment data is daily; intraday sentiment shifts are not captured.
- Sentiment categories were simplified into two regimes.
- Analysis is **correlational**, not causal.
- Trade size is used as a proxy for risk due to lack of explicit leverage data.

---

## 📁 Repository Structure

├── Trader_Behavior_vs_Market_Sentiment.ipynb # Data analysis (Colab-ready)
├── Trader_Behavior_Risk_Analysis.pbix # Power BI dashboard
├── dashboard.png # Dashboard preview
└── README.md # Project documentation

---

##  Author
**Vinay**  
Junior Data Scientist Candidate  
Focus: Data Analysis, Trading Analytics, Risk Insights

---

##  Conclusion
This project demonstrates that **market sentiment primarily affects trader risk behavior rather than win probability**.  
Understanding this distinction is critical for building robust trading systems, evaluating traders, and designing sentiment-aware risk controls.


