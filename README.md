# Neuro-Symbolic AI Forecasting: The Symbolic Seam

## What It Does
Combines neural forecasting (LSTM) with Knowledge Graph constraints via Quadratic Programming. Ensures predictions respect real-world limits — even during crises.

## Key Results
| Condition | Neural Baseline | Symbolic Seam |
|-----------|---|---|
| Normal markets | RMSE 3.698 | RMSE 3.695 (identical) |
| Black Swan crisis | 95.33% violations | 6.00% violations ✅ |
| Violations prevented | — | **938 / 1,050** |

## How It Works
1. **System 1 (LSTM)**: Predicts prices from historical data
2. **System 2 (KG)**: Defines operational bounds (min/max price, daily change limit)
3. **Symbolic Seam**: Projects forecast into constraint space using QP solver

## Quick Start
```bash
pip install yfinance cvxpy torch pandas scikit-learn -q
jupyter notebook Neuro_Symbolic_Forecasting_Kaggle.ipynb
```

## Dataset
- **Source**: Yahoo Finance (yfinance)
- **Stocks**: 50 S&P 500 stocks
- **Period**: Jan 2020 – Jan 2024
- **Sequences**: 48,800 (30-day windows)

## Model
- LSTM: 64 hidden, 2 layers
- Training: 15 epochs, batch 64
- Best val loss: 0.000539

## Key Findings
- **Normal**: Zero accuracy penalty (3.698 → 3.695 RMSE)
- **Crisis**: 89.33pp improvement in constraint compliance (95.33% → 6.00% violations)
- **Per-stock**: High-volatility stocks improve most (CRM +5.2%, DHR +1.7%)

## Why This Matters
Neural models fail when rules change (tariffs, limits, regulations). Symbolic Seam enforces hard constraints at inference time without retraining.

## Files
- `Neuro_Symbolic_Forecasting_Kaggle.ipynb` — Single notebook, all stages
- `IEEE_Symbolic_Seam_Full.docx` — Full research paper
- `models_backup_50stock.zip` — Trained model + config

## Author
Sanaullah Tareen | PAF-IAST | [@SanaullahTareen](https://github.com/SanaullahTareen)

---

Full details in IEEE paper or Kaggle notebook.
