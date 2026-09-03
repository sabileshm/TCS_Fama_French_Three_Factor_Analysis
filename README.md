# Fama-French Three-Factor Analysis of Tata Consultancy Services (TCS)

## Overview

This project applies the **Fama-French Three-Factor Model** to analyze the historical excess returns of **Tata Consultancy Services (TCS)**.

The objective is to estimate TCS's exposure to three systematic risk factors:

* **Market Risk Premium (Mkt-RF)**
* **Size Factor (SMB)**
* **Value Factor (HML)**

The analysis uses Python for data collection, preparation, statistical modelling, regression analysis, and visualization.

---

## Research Objective

The primary objective is to determine whether TCS's historical excess returns can be explained by its exposure to the Fama-French market, size, and value factors.

The regression model is:

**Rᵢ − Rf = α + β₁(Mkt−Rf) + β₂(SMB) + β₃(HML) + ε**

Where:

* **Rᵢ** = TCS return
* **Rf** = Risk-free rate
* **α** = Regression alpha
* **β₁** = Market factor loading
* **β₂** = SMB factor loading
* **β₃** = HML factor loading
* **ε** = Regression residual

---

## Data

### Equity Data

Historical market data for **TCS.NS** is obtained using `yfinance`.

The analysis calculates daily percentage returns from the historical adjusted closing prices.

### Fama-French Factors

The analysis incorporates the following factors:

* Mkt-RF
* SMB
* HML
* RF

The equity returns and factor data are aligned by date before performing the regression.

### Sample Period

**August 2021 – July 2026**

---

## Methodology

The analysis follows these steps:

1. Download historical TCS price data.
2. Calculate daily TCS returns.
3. Obtain Fama-French factor data.
4. Align the stock and factor datasets by date.
5. Calculate TCS excess returns.
6. Specify the Fama-French three-factor regression.
7. Estimate the regression using Ordinary Least Squares (OLS).
8. Evaluate coefficient significance using p-values and t-statistics.
9. Analyze model explanatory power using R² and adjusted R².
10. Visualize the estimated factor loadings.

### Analytical Workflow

```text
TCS Historical Prices
        ↓
Daily Returns
        ↓
Fama-French Factor Data
        ↓
Date Alignment & Data Cleaning
        ↓
TCS Excess Returns
        ↓
OLS Regression
        ↓
Factor Loadings & Statistical Tests
        ↓
Investment Interpretation
```

---

## Key Results

| Variable | Coefficient |    P-value | Interpretation                       |
| -------- | ----------: | ---------: | ------------------------------------ |
| Alpha    |     -0.0563 |      0.165 | Not statistically significant        |
| Mkt-RF   |  **0.1900** | **<0.001** | Significant positive market exposure |
| SMB      |     -0.0375 |      0.552 | Not statistically significant        |
| HML      |     -0.0201 |      0.683 | Not statistically significant        |

### Model Statistics

* **Observations:** 1,150
* **R²:** 0.024
* **Adjusted R²:** 0.021
* **F-statistic:** 9.40
* **Prob (F-statistic):** 3.36e-06

---

## Interpretation

### Market Exposure

The estimated **Mkt-RF coefficient of 0.1900** is statistically significant.

This indicates that TCS had a positive exposure to the market risk premium during the sample period. However, the magnitude of the coefficient indicates relatively limited sensitivity to movements in the market factor compared with a stock having a beta close to one.

### Size Exposure — SMB

The estimated SMB coefficient is **-0.0375** and is not statistically significant.

Therefore, the analysis does not provide sufficient statistical evidence that TCS had a meaningful systematic exposure to the size factor during the sample period.

### Value Exposure — HML

The estimated HML coefficient is **-0.0201** and is also not statistically significant.

The results therefore do not provide sufficient evidence of a meaningful systematic value-factor exposure.

### Alpha

The estimated alpha is **-0.0563**, but its p-value of **0.165** means that it is not statistically significant at conventional significance levels.

Therefore, the analysis does not provide sufficient evidence of abnormal returns after controlling for the three Fama-French factors.

### Model Explanatory Power

The model's **R² of 0.024** indicates that approximately 2.4% of the variation in TCS's daily excess returns is explained by the three factors included in this specification.

This suggests that substantial variation in TCS's daily returns remains unexplained by the Fama-French three-factor model.

---

## Investment Research Perspective

The analysis suggests that TCS's historical daily excess returns were significantly related to the market risk premium, while the estimated size and value exposures were statistically insignificant.

The low R² also indicates that the three-factor model alone provides limited explanatory power for TCS's daily return movements over the sample period.

These results demonstrate the importance of considering additional company-specific and market factors when evaluating the return behaviour of an individual technology-services stock.

---

## Limitations

This analysis has several limitations:

* The results are based on historical data and do not imply future performance.
* The Fama-French three-factor model may not fully capture the return-generating process of an individual stock.
* The relatively low R² indicates limited explanatory power.
* SMB and HML exposures are statistically insignificant in this specification.
* Daily financial returns may exhibit non-normality.
* The regression uses conventional OLS standard errors rather than heteroskedasticity/autocorrelation-robust standard errors.
* The analysis should not be interpreted as a standalone investment recommendation.

---

## Technologies & Libraries

The project uses:

* Python
* Pandas
* NumPy
* Matplotlib
* Statsmodels
* yfinance
* pandas-datareader
* OpenPyXL

---

## Repository Contents

| File                             | Description                                |
| -------------------------------- | ------------------------------------------ |
| `TCS_Fama_French_Analysis.ipynb` | Complete Python analysis                   |
| `Regression_Summary.txt`         | Regression output summary                  |
| `Regression_Coefficients.xlsx`   | Regression coefficients and statistics     |
| `Factor_Loadings.png`            | Visualization of estimated factor loadings |
| `requirements.txt`               | Python dependencies                        |
| `README.md`                      | Project documentation                      |

---

## Disclaimer

This project is intended for **academic and educational purposes** and represents historical statistical analysis. It does not constitute investment advice or a recommendation to buy or sell any security.
