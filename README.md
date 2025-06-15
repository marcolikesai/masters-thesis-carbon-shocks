# masters-thesis-carbon-shocks

# The Effect of EU-ETS Carbon-Price Shocks on Green/Brown-Energy Equity Performance and Volatility

**Authors:** Aditya Rohatgi, Marco Montenegro, Vicente Puga, Jesse Mason  
**Supervisors:** Dr. Jacqueline Doremus  
**Institution:** California Polytechnic State University, MS Quantitative Economics, 2025

---

## Overview

This repository contains all analysis and code for our master’s thesis studying the **real-time impact of carbon price shocks under the EU-ETS on green and brown energy equities**.  
We combine event study, regression, volatility modeling (GARCH, LSTM), and causal machine learning (Causal Forest) methods to uncover how markets price transition risk.

---

## Research Questions

- **Do EU-ETS carbon price shocks create significant abnormal returns for green (ICLN) and brown (XLE) energy stocks?**
- **How do these shocks affect short-term volatility?**
- **Can modern ML methods (LSTM, Causal Forest) improve upon traditional models for prediction and causal interpretation?**
- **What is the role of macro controls (oil, VIX, interest rates)?**

---

## Project Structure

- `/data/`: Sample data and data schema (main data available on request).
-  `/notebooks/`: Jupyter Notebooks for every stage of analysis (see below)
- `/results/`: Output tables, figures, and logs.

---

## Methodology

### **1. Data Collection**
- **Timeframe:** 2018–2024, daily frequency
- **Data:**  
  - EU-ETS carbon price (front-month EUA futures)
  - Green stocks: ICLN ETF
  - Brown stocks: XLE ETF
  - Macro controls: Brent oil, VIX, 10Y UST yields, SP500

### **2. Shock Detection**
- Fit AR(5) model to carbon price returns.
- Define "shock days" where residual > 1.5 std deviations.

### **3. Event Study**
- For each shock day, analyze 10 days before/after:  
  - Cumulative Abnormal Returns (CAR)  
  - Realized Volatility

### **4. Regression Analysis**
- OLS regressions on returns and volatility, controlling for market factors.

### **5. Volatility Forecasting**
- **GARCH(1,1):** Econometric benchmark (ARCH package)
- **LSTM:** Deep learning model (TensorFlow/Keras)

### **6. Causal Forest (EconML)**
- Estimate Average Treatment Effect (ATE) and Conditional ATE (CATE)  
- Robustness: Placebo tests, threshold variation, additional controls

---
