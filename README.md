# Trader Performance vs Market Sentiment

## Objective
Analyze how Bitcoin market sentiment (Fear vs Greed) influences trader behavior and performance on Hyperliquid.  
The goal is to uncover patterns that can inform better trading strategies.

---

## Datasets

### 1. Bitcoin Market Sentiment
- Columns: Date, classification (Fear / Greed)

### 2. Historical Trader Data
- Includes:
  - Account
  - Execution Price
  - Size USD
  - Side (Long/Short)
  - Timestamp
  - Closed PnL
  - Fees, Trade ID, etc.

---

## Methodology

### 1. Data Cleaning & Preparation
- Removed duplicates and handled missing values  
- Fixed timestamp issues (resolved incorrect epoch parsing issue)  
- Used `Timestamp IST` for correct datetime conversion  
- Standardized both datasets to **daily level**

### 2. Data Alignment
- Created a common `date` column using datetime flooring  
- Merged both datasets on `date`  

### 3. Feature Engineering
- Daily PnL per trader  
- Win rate (% of profitable trades)  
- Trade frequency (trades per day)  
- Trade size (USD exposure as proxy for risk)  
- Long vs Short ratio  

---

## Key Insights

### 1. Lower performance during Fear periods
- Traders experience higher losses during Fear  
- Likely driven by panic selling and high volatility  

### 2. Increased activity during Greed
- Trade frequency rises during Greed phases  
- Suggests overconfidence and aggressive trading  

### 3. High-risk trades show inconsistent results
- Larger trade sizes lead to higher variance in PnL  
- Indicates unstable performance among high-risk traders  

---

## Visualizations
- Boxplot: PnL distribution (Fear vs Greed)  
- Crosstab: Long/Short behavior  

> All visualizations are included in the notebook.

---

## Strategy Recommendations

### Strategy 1: Reduce risk during Fear
- Lower position sizes during Fear periods  
- Helps avoid large drawdowns in volatile markets  

### Strategy 2: Avoid overtrading during Greed
- Limit trade frequency in Greed phases  
- Reduces exposure to false breakouts  

---

## Key Takeaway
Market sentiment significantly influences trader behavior and performance.  
Adapting strategies based on sentiment can improve consistency and reduce risk.

---

## Tech Stack
- Python (Pandas, NumPy)  
- Matplotlib, Seaborn  
- Jupyter Notebook / Google Colab  

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/your-repo-name.git

# 2. Open notebook
cd your-repo-name

# 3. Run in Jupyter/Colab
