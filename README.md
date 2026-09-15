# 📈 Indonesian Worker Welfare Dynamics: Econometric Modeling & Time Series Forecasting (CRISP-DM)

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-SARIMA-blue?style=for-the-badge)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Regression-orange?style=for-the-badge&logo=scikitlearn&logoColor=white)
![CRISP-DM](https://img.shields.io/badge/Methodology-CRISP--DM-green?style=for-the-badge)

An empirical macroeconomic and predictive analytics study investigating the relationship between household consumption, provincial minimum wages (UMP), and monthly income across Indonesian provinces (2015–2022) using Badan Pusat Statistik (BPS) data. The project pairs multiple regression analysis with a 5-year SARIMA forecasting model for East Java (*Jawa Timur*).

---

## 👤 My Role & Contributions
* **Data Preprocessing & EDA:** Aggregated and structured regional macroeconomic indicators from BPS datasets (2015–2022), performed missing value checks, and configured 80/20 train-test splits.
* **Econometric Modeling:** Designed and evaluated a Multiple Linear Regression model in Python to estimate expenditure elasticity relative to wages and provincial minimum wages (UMP).
* **Time Series Forecasting:** Configured, fitted, and validated a SARIMA time series model to project 5-year provincial wage trends for East Java (2023–2027) evaluated via MSE and MAPE.

---

## 📌 Research Overview & Core Findings

```text
Dataset Source       : Badan Pusat Statistik (BPS) Indonesia
Timeline Coverage    : 2015 – 2022
Forecasting Horizon  : 5 Years (2023 – 2027) for East Java (Jawa Timur)
Evaluation Split     : 80% Train, 20% Test
SARIMA Model Metrics : MSE = 302,030.64 | MAPE = 0.0363 (~3.63% error)
```
---

## Key Analytical Takeaways
-	Wage-Expenditure Elasticity: Multiple regression reveals that monthly wage growth is the primary positive driver of provincial expenditure capacity, with baseline statutory minimum wages (UMP) providing a stabilizing secondary effect. 
-	East Java Wage Trajectory (2023-2027): Time series projections identify wage expansion peaking in 2024 before entering a slight downward stabilization through 2027.
-	Policy Implication: Minimum wage policies correlate with higher monthly wages, but disparate living cost ratios across provinces highlight the need for regionally targeted economic adjustments.

---
<p align="center">
<img width="814" height="818" alt="19AKm9VtuBG2WnCoxjCXcaA" src="https://github.com/user-attachments/assets/a668fb6d-d95e-47b7-89d6-af9a2b07378d" /></p>

## 🔄 CRISP-DM Project Lifecycle
### 1. Business Understanding
•	Core Objective: Analyze socioeconomic welfare factors across Indonesian provinces to evaluate whether wage growth keeps pace with household living costs. 
•	Sub-Objectives:
  1.	Measure the impact of UMP on average monthly wages and overall welfare. 
  2.	Identify disparities between regional income levels and living costs. 
  3.	Forecast regional wage dynamics over a 5-year horizon to support evidence-based policy planning. 
### 2. Data Understanding & Preparation
•	Source: Historical socioeconomic metrics from BPS covering wages, poverty rates, per capita spending, and regional UMP. 
•	Preprocessing: Handled null values, normalized features, and structured the modeling data split at 80% training / 20% testing. 
•	Tooling: Python via Visual Studio Code using Pandas, NumPy, Matplotlib, and Seaborn. 

## 🖼️ Visual Analysis & Model Interpretations

<p align="center"><img width="419" height="421" alt="image" src="https://github.com/user-attachments/assets/31709182-d30d-4444-bb44-e0007c9cd3b0" /></p>

### 1. Feature Distributions & Multicollinearity (Pairplot Analysis)
What This Visual Displays
•	Multi-panel scatter plot matrix and distribution histograms mapping the interactions between Upah (Wages), UMP (Provincial Minimum Wage), and Pengeluaran (Household Expenditure). 
Analytical Interpretation
•	The scatter distributions confirm a strong positive linear tendency between provincial wages and expenditure levels. 
•	UMP distributions show cluster concentrations around specific baseline wage bands, validating its use as an exogenous regulatory variable alongside actual wages. 

<p align="center"><img width="505" height="367" alt="image" src="https://github.com/user-attachments/assets/3c13cfe7-2264-426f-87a3-ba0fcfcddbe0" /></p>

### 2. Historical Wage Growth in East Java (2015–2022)
What This Visual Displays
•	Longitudinal line graph depicting the continuous progression of recorded wages in East Java across the 8-year observation baseline. 
Analytical Interpretation
•	East Java demonstrated sustained wage expansion from 2015 through 2022, rising from ~9,200 to over 15,000. 
•	The steep growth curve from 2015 to 2017 gradually transitioned into steady gains, setting the historical baseline for time series auto-regressive decomposition. 

<p align="center"><img width="522" height="155" alt="image" src="https://github.com/user-attachments/assets/a25250c7-3461-4918-9c57-ff216f622679" /></p>

### 3. 5-Year Wage Projection vs. Actuals (SARIMA)
What This Visual Displays
•	Combined plot overlaying actual historical data points (blue dots) against the 5-year projected path (orange line with markers) spanning 2023 through 2027. 
Analytical Interpretation
•	The model captures continuity from historical data, projecting initial upward momentum through 2024 before forecasting a slight decline through 2027. 
•	This cooldown curve signals potential external pressures such as shifting labor demand or macroeconomic adjustments that regional planners must account for. 

---

## 📐 Mathematical Formulations & Statistical Models
### 1. Multiple Linear Regression Model
Formulated to quantify expenditure (Y) based on actual worker wages (X_1) and regional UMP (X_2):

$$
Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2
$$

Derived regression parameters: 
$$ 
"Pengeluaran"=323,701.55+15.81⋅"Upah"+0.01⋅"UMP" 
$$

Empirical Application Examples
- Surabaya Simulation: For a baseline wage of IDR 5,000,000 and UMP of IDR 1,000,000, the predicted expenditure baseline stands at approximately IDR 79,383,701. 
- Jakarta Simulation: For a baseline wage of IDR 7,500,000 and UMP of IDR 1,500,000, the predicted expenditure scales to approximately IDR 118,913,705. 

### 2. Time Series Modeling (SARIMA)
- Model Configuration: Configured with non-seasonal baseline parameters (seasonal=False) across a 12-month sequence to capture annual adjustments. 
- Target Area: East Java (Jawa Timur) labor market. 

#### 5-Year Forecast Projections
| Year | Projected Wage Value | Trajectory Note |
| :---: | :---: | :--- |
| 2023 | 15,091 | Baseline post-observation year |
| 2024 | 15,182 | Forecasted expansion peak |
| 2025 | 15,013 | Slight growth deceleration |
| 2026 | 14,846 | Continued market cooling |
| 2027 | 14,681 | Projected low within 5-year cycle |

### Model Validation & Accuracy Metrics
Mean Squared Error (MSE): 302,030.64

### Mean Absolute Percentage Error (MAPE): 0.0363 (~3.63% error margin, confirming high predictive reliability)

---

<p align="center"><img width="2480" height="3508" alt="Infographic_Kelompok 7_page-0001" src="https://github.com/user-attachments/assets/5c8b3b8c-3b16-4f3c-986f-8a6500c4d21a" /></p>
