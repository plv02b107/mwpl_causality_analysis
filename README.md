# MWPL Causality Analysis

## Research Question

This study investigates whether **Market Wide Position Limit (MWPL%)**, a regulatory utilization metric from NSE- contains predictive information for **next-day stock returns**.

---

## Dataset

* 205 NSE-listed stocks
* 52 trading days (Feb 2026 – May 2026)
* ~10,600 stock-day observations after cleaning
* Variables: MWPL%, Open Interest change, prices, and derived return features

---

## Methodology

The analysis follows a structured causal pipeline:

1. **Stationarity Testing (ADF)**
   Ensures variables are suitable for time-series modeling

2. **Two-Way Fixed Effects Panel Regression**
   Controls for:

   * Stock-specific effects
   * Market-wide daily shocks

3. **Entity-Level Granger Causality**
   Tests direction:

   * MWPL ->Returns
   * Returns -> MWPL
     Uses BH correction for multiple testing

4. **High MWPL Event Study**
   Examines returns near extreme MWPL levels (70–95%)

5. **Cross-Sectional Long-Short Strategy**
   Top vs bottom MWPL stocks each day

6. **Regression Discontinuity (95% Threshold)**
   Exploits NSE ban rule as a quasi-natural experiment

7. **Walk-Forward Backtest (with transaction cost)**
   Evaluates real-world viability

---

## Key Findings

### 1. No Robust Stock-Level Alpha

* Panel regression shows **MWPL changes are not statistically significant**
* Effect disappears after controlling for:

  * Stock fixed effects
  * Time effects
  * Serial correlation

---

### 2. Reverse Causality Dominates

* MWPL -> Returns: **~0.5% significant (BH corrected)**
* Returns -> MWPL: **~29% significant**

**Interpretation:**
Price movements drive positioning (MWPL), not the other way around.
MWPL behaves as a **lagging crowding indicator**, not a predictive signal.

---

### 3. Weak Evidence at Extreme Thresholds

* Limited observations near 90–95% MWPL
* RD at 95% shows **positive but statistically weak effect (p ≈ 0.08)**

**Interpretation:**
Possible short-covering dynamics near ban threshold, but not robust.

---

### 4. No Tradeable Signal After Costs

* Walk-forward test shows **no consistent positive net returns**
* Results deteriorate after transaction costs

---

## Conclusion

There is **no strong evidence that MWPL predicts next-day stock returns** in the current sample.

Instead:

* MWPL reflects **market positioning and crowding**
* Not a reliable standalone alpha signal

---

## Why This Study Matters

Despite a null result, the study is valuable because it follows a **disciplined research framework**:

* Avoids spurious correlations
* Corrects for multiple testing
* Uses out-of-sample validation
* Incorporates realistic transaction costs

---

## Limitations

* Short sample (52 trading days)
* Very few observations near 95% threshold
* No market-adjusted alpha (Nifty)

---

## Next Steps

* Extend dataset (6-12 months)
* Test regime dependence (high volatility periods)
* Explore sector-level effects
* Study intraday behavior near 95% threshold

---
