# Empirical Data and Statistical Regression Analysis

[![Tool: Microsoft Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?logo=microsoft-excel&logoColor=white)](#)
[![Focus: Regression & Isotherm Modeling](https://img.shields.io/badge/Focus-Regression%20%26%20Error%20Analysis-blue)](#)

## Project Overview
This project performs an empirical analysis and statistical evaluation of batch adsorption equilibrium for methylene blue (MB) dye removal using activated carbon (AC). Using spectrophotometric concentration data, empirical observations are transformed and evaluated against five classical two-parameter adsorption isotherm models to identify the governing surface mechanism and quantify system performance.

---

## Key Objectives
- Transform raw absorbance readings into equilibrium concentration ($c_e$) and capacity ($q_e$) values via a linear calibration standard.
- Perform linear regression to evaluate the fit of five standard isotherm models: **Henry's Law**, **Freundlich**, **Langmuir**, **Frumkin**, and **Temkin**.
- Conduct non-linear statistical validation across multiple error functions ($R^2$, SSE, $\chi^2$, ARE, RMSE, MPSD) to establish the best-fit model.
- Characterize the thermodynamic nature of the adsorption process (physisorption vs. chemisorption) using the **Dubinin-Radushkevich (D-R)** model.
- Model a single-stage batch treatment reactor prototype to size adsorbent mass requirements for targeted pollutant removal.

---

## Methodology & Workflow

### 1. Calibration Curve & Data Transformation
- Measured optical absorbance across standard MB concentrations (0.02–0.10 g/L) at $\lambda = 660\text{ nm}$.
- Derived standard linear calibration equation:  
  $$A = 2.63 \cdot C + 1.145 \quad (R^2 = 0.9972)$$
- Calculated residual concentrations ($c_e$) and equilibrium adsorption capacity ($q_e$, mg/g) using mass balance principles across five test concentrations (0.2–1.0 g/L).

### 2. Isotherm Regression Models
Each linearized model was mapped against experimental values:
- **Henry's Law:** $q_e = K_H c_e + I$
- **Freundlich:** $\ln(q_e) = \frac{1}{N}\ln(c_e) + \ln(K_F)$
- **Langmuir:** $\frac{c_e}{q_e} = \frac{c_e}{q_{\max}} + \frac{1}{q_{\max}K_L}$
- **Frumkin:** $\ln\left[\frac{\theta}{(1-\theta)c_e}\right] = \ln(K_{FG}) - \frac{2W}{RT}\theta$
- **Temkin:** $q_e = \frac{q_{\max}RT}{b_T}\ln(c_e) + \frac{q_{\max}RT}{b_T}\ln(A_T)$

---

## Results & Statistical Error Analysis

| Model | Linear Equation | Parameters | Linear $R^2$ | Non-Linear $R^2$ | SSE | $\chi^2$ | RMSE |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **Temkin** | $q_e = 25.93\ln(c_e) + 122.4$ | $A_T = 112.21\text{ L/g}$, $B_T = 0.223$ | **0.9972** | **0.9972** | **6.73** | **0.2429** | **1.497** |
| **Langmuir** | $\frac{c_e}{q_e} = 0.0086c_e + 0.0007$ | $q_{\max} = 116.28\text{ mg/g}$, $K_L = 12.29\text{ L/g}$ | 0.9786 | 0.9870 | 31.47 | 1.0059 | 3.239 |
| **Freundlich** | $\ln(q_e) = 0.6037\ln(c_e) + 5.4729$ | $K_F = 238.15$, $N = 1.656$ | 0.9353 | 0.9264 | 178.15 | 3.5000 | 7.706 |
| **Henry's Law** | $q_e = 315.58c_e + 23.183$ | $K_H = 315.58\text{ L/g}$ | 0.8881 | 0.8881 | 270.87 | 4.2097 | 9.502 |
| **Frumkin** | $\ln\left[\frac{\theta}{(1-\theta)c_e}\right] = 0.1083\theta + 2.3982$ | $K_{FG} = 11.00$ | 0.0341 | — | — | — | — |

---

## Key Findings
1. **Best Fit Model:** The **Temkin isotherm** yielded the highest correlation ($R^2 = 0.9972$) and the lowest error metrics ($\text{SSE} = 6.73$, $\chi^2 = 0.2429$), indicating an energetically heterogeneous adsorbent surface where adsorption heat decreases linearly with coverage[cite: 10, 44, 45, 47].
2. **Adsorption Mechanism:** Dubinin-Radushkevich analysis returned a mean free energy $E = 5.0\text{ kJ/mol}$[cite: 10, 41, 46, 47]. Because $E < 8.0\text{ kJ/mol}$, the mechanism is verified as **physisorption** driven primarily by weak Van der Waals forces[cite: 10, 26, 46, 47].
3. **Batch Reactor Design Prototype:** Applying the Temkin model parameters to design a batch remediation system for $10\text{ L}$ of wastewater ($c_0 = 2.5\text{ g/L}$) at a $90\%$ removal target ($c_e = 0.25\text{ g/L}$) determined a required adsorbent mass of **$0.26\text{ kg}$**[cite: 10, 46, 47].

---

## Repository Contents
- `Adsorption_Isotherm_Regression_Analysis.xlsx`: Master workbook containing experimental absorbance raw data, calibration curve, linear regression plots, fitted isotherm calculations, and error functions.
- `README.md`: Project background, theoretical formulation, statistical validation, and findings.
