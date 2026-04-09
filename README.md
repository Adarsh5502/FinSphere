# FinSphere

Stock price prediction for Tata Consumer Products Ltd using K-Nearest Neighbors (KNN).

## What It Does

Trains two KNN models on 15 years of stock data:
- **Classification**: Predict if price goes up or down (binary)
- **Regression**: Predict exact closing price

Uses 2 features: Open-Close difference, High-Low range

## Expected Results

| Metric | Expected | Notes |
|--------|----------|-------|
| Test Accuracy | 48-52% | Close to baseline (50%) |
| Baseline | 50% | Random guessing |
| RMSE | ₹20-40 | Prediction error |
| Optimal K | 5-8 | From grid search |

**Key Finding**: Test accuracy near baseline means simple price features don't predict future prices.

## Why It Fails

- Only 2 features (markets respond to 1000+ factors)
- Random train-test split breaks time-series structure
- KNN can't recognize trends
- Market prices follow random walk properties

This is intentional — the project demonstrates why naive ML fails on financial data.

## How to Run

```bash
pip install pandas numpy scikit-learn matplotlib yfinance jupyter
jupyter notebook FinsphereFinal.ipynb
```

Runtime: 2-5 minutes (first run downloads data)

## What Each Cell Does

1. Import libraries & download data
2. Plot historical prices
3. Create features (Open-Close, High-Low)
4. Create target (up/down classification)
5. Train-test split (75-25)
6. Train KNN classifier with grid search
7. Plot predictions vs actual
8. Train KNN regressor
9. Calculate RMSE
10. Plot regression comparison

## Data

- Stock: TATACONSUM.NS (Tata Consumer Products)
- Period: 2010-2025 (15 years, 3,767 trading days)
- Source: Yahoo Finance

## Files

- `FinsphereFinal.ipynb` - Main notebook
- `TATACONSUM.NS_stock_data.csv` - Historical data
- `README.md` - This file

## Key Insight

This project teaches more through failure than success. Poor results prove that **historical prices alone cannot reliably predict future prices** — a fundamental truth in financial markets.

## Disclaimer

Educational purposes only. Not a trading tool. Consult a financial advisor before investing.