
# 📈 ML-Enhanced Pair Trading Strategy: HDFC Bank vs ICICI Bank

This project implements a **market-neutral statistical arbitrage strategy** using **pair trading** between HDFC Bank and ICICI Bank. It combines classical cointegration-based methods with **machine learning (Random Forest)** to predict entry and exit points based on engineered features from the spread.

---

## 🔍 Objective

To identify trading opportunities where the price difference (spread) between HDFCBANK and ICICIBANK deviates from its statistical mean — and build a smarter, ML-driven strategy to trade those deviations profitably.

---

## ⚙️ Technologies Used

- Python
- yFinance, pandas, numpy
- statsmodels (cointegration, ADF test)
- scikit-learn (Random Forest)
- matplotlib, seaborn

---

## 🧠 Strategy Components

1. **Data Collection**: Daily close prices (2015–2024)
2. **Correlation & Cointegration**: Test long-term relationship
3. **Spread Calculation**: Spread = HDFC - β × ICICI
4. **Z-score Normalization**: Detect mean-reverting signals
5. **Feature Engineering**: Spread momentum, volatility, rolling stats
6. **ML Signal Prediction**: Random Forest predicts Buy/Sell/Hold
7. **Backtest**: Simulated trading and cumulative returns

---

## 📊 Visual Insights

This project includes three key visualizations to demonstrate the logic and effectiveness of the ML-based pair trading strategy on HDFC Bank and ICICI Bank.

### 📈 1. Z-Score of Spread

![Z-Score Plot](images/zscore_plot.png)

The Z-score represents how far the current spread deviates from its historical mean, measured in standard deviations over a 30-day rolling window.

- **+1 Z-score** → Potential **Sell** opportunity (mean expected to decrease)
- **-1 Z-score** → Potential **Buy** opportunity (mean expected to increase)

📌 This forms the **foundation** for detecting mean-reverting signals in the spread.

---

### 📉 2. Spread with ML-Generated Buy/Sell Signals

![Signal Plot](images/signal_plot.png)

The spread between HDFCBANK and ICICIBANK is plotted along with **ML-generated trade signals**:

- **Green ▲** → Buy signal (Long HDFC, Short ICICI)
- **Red ▼** → Sell signal (Short HDFC, Long ICICI)

📌 This shows how the **Random Forest model** captures profitable entry points by learning from past spread dynamics, volatility, and Z-score behavior.

---

### 💰 3. Cumulative Return of Strategy

![Cumulative Return](images/cumulative_return.png)

This equity curve visualizes the **cumulative PnL** from all trades made based on ML-predicted signals.

- Demonstrates the **profitability** and **consistency** of the strategy over time
- Reflects **risk-adjusted alpha generation** through statistical arbitrage

📌 A rising curve confirms that the strategy is not only theoretically sound but also **financially effective**.

---

## 📁 File Structure

```
├── pair_trading_notebook.ipynb
├── README.md
├── data/
│   └── hdfc_icici_pair_data.csv
├── images/
│   └── zscore_plot.png
│   └── signal_plot.png
│   └── cumulative_return.png
└── strategy_results.csv
```

---


