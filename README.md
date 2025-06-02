# Black-Litterman Portfolio Strategy App

This project implements a sentiment-driven investment strategy using the Black-Litterman model. The app simulates optimized portfolio allocations, incorporating realistic features such as transaction costs, volatility constraints, and turnover penalties.

**Live App**: [Launch on Streamlit](https://black-litterman-webapp-kwpv7sccwkp72qtaydz967.streamlit.app)

---

## Project Highlights

- **Custom strategy**: Developed from scratch with full autonomy in model choice, signals, and constraints
- **Black-Litterman framework**: Integrates investor views into asset allocation using a Bayesian approach
- **Sentiment signals**: Extracted from Stocktwits to reflect crowd behavior on individual assets
- **Rolling regressions**: Used to estimate sensitivity of returns to sentiment changes (with t-stat scaling)
- **Realistic features**: Turnover penalties, volatility targeting, no short-selling or leverage
- **Full backtesting**: Evaluates performance under varying regimes and parameter settings
- **Full methodology and model details are explained interactively in the app itself.**  
Includes all formulas, assumptions, signal construction logic, and constraint design.

---

## ⚙️ How It Works

### 1. **Signal Generation**
- Polarity scores derived from Stocktwits message classification (bullish vs bearish)
- Daily changes in polarity used as predictive signals

### 2. **Regression & View Construction**
- Rolling regression estimates return sensitivity to polarity
- Views (Q) adjusted by confidence scores based on t-statistics and volatility

### 3. **Omega Matrix**
- Encodes uncertainty using a confidence-scaling formula
- High variance or weak signals → higher Omega → less weight in optimization

### 4. **Optimization**
- Objective: maximize expected return – risk penalty – turnover penalty
- Constraints: fully invested, no short-selling, no leverage
- Output: Cumulative return, volatility, Sharpe ratio, drawdown, and more

---

## 🗂️ Folder Structure

```
.
├── app.py                  # Streamlit app
├── core/                   # Core model and utility files
│   ├── strategy.ipynb  
├── results/                # CSVs with backtested results
├── requirements.txt        # Python dependencies
└── README.md
```

---

## 📊 Example Output

- Interactive charts (Altair): total returns, drawdown, allocation dynamics
- Portfolio metrics: Sharpe ratio, turnover, volatility, max drawdown

---

## 👤 Author

Rémy David  
Master's in Finance (Asset & Risk Management) — HEC Lausanne  
Contact: [remy.david@unil.ch](mailto:remy.david@unil.ch)

---

## 📝 License

This project is for educational and demonstration purposes only.
