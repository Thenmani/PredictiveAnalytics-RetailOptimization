# Laptop Sales — Predictive Analytics for Retail Optimization

Predictive modeling on laptop sales dataset to support **pricing strategy** and **inventory planning** for a consumer electronics retailer.

## Project Overview

Built and evaluated regression models that predict a laptop's **Retail Price** from its hardware specifications. The work is organized into three phases, moving from a simple model to an optimized one.

## Dataset

- ~7,956 laptop sales transactions
- **Target:** Retail Price 
- **Features:** HD Size (GB), RAM (GB), Battery Life (Hours), Processor Speed (GHz), Integrated Wireless (Yes/No), Bundled Applications (Yes/No)

## Phases & Key Results

### Phase 1 — Simple Linear Regression
Modeled price using **HD Size only**.
- R² = **0.236**, p-value ≈ 0
- **Takeaway:** Storage is a statistically significant but weak standalone predictor — it explains only ~24% of price variation.

### Phase 2 — Multiple Linear Regression
Added **RAM, Battery Life, Processor, Wireless, and Bundled Apps**.
- Adjusted R² jumped to **0.928**
- No problematic multicollinearity (all VIFs acceptable)
- Each spec adds a fixed price premium (e.g., +51/battery hour, +49/GB RAM, +50 for bundled apps)

### Phase 3 — Predictive Deployment & Optimization
- **Forecast (Model 1):** 2000 GB laptop → ~1,027
- **Forecast (Model 2):** 2000 GB, 44 GB RAM, 4 hr battery → ~3,079
- Both are extrapolations beyond the training range, so confidence is limited.
- **Optimization:** Encoding tiered specs as categorical variables reduced MSE to **~0**, revealing that Retail Price is a deterministic, rule-based "price book" rather than a noisy market price.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/REPO_NAME.git
   ```
2. Install the required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels
   ```
3. Open the notebook and run all cells top to bottom:
  

## Tools Used

Python · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · statsmodels

## Key Business Insight

Pricing in this dataset is purely rule-based (fixed premiums per spec) with no market noise. This suggests an opportunity to test **demand-driven pricing** instead of fixed cost-plus pricing.
