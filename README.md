# Empirical Data and Statistical Regression Analysis

[![Tool: Microsoft Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?logo=microsoft-excel&logoColor=white)](#)
[![Focus: Regression & Isotherm Modeling](https://img.shields.io/badge/Focus-Regression%20%26%20Error%20Analysis-blue)](#)

## Overview
This project focuses on evaluating equilibrium batch adsorption data for methylene blue (MB) dye removal using activated carbon (AC). Using spectrophotometric readings, raw absorbance data was converted into equilibrium parameters and fitted against standard adsorption isotherms in Microsoft Excel to evaluate surface behavior, test model validity, and determine sizing requirements for a treatment unit.

---

## What Was Done

1. **Calibration & Concentration Mapping:**
   - Prepared standard MB solutions across a 0.02–0.10 g/L concentration range at 660 nm to generate a spectrophotometric calibration line:
     $$A = 2.63 \cdot C + 1.145 \quad (R^2 = 0.9972)$$
   - Evaluated five batch adsorption trials (initial concentrations $c_0$ from 0.2 to 1.0 g/L, 100 mL volume, 1.0 g activated carbon, shaken at 150 rpm for 40 min).
   - Determined residual equilibrium concentrations ($c_e$) and solid-phase loading ($q_e$, mg/g) using mass balance.

2. **Isotherm Linearization & Parameter Extraction:**
   - Linearized and plotted five two-parameter models: **Henry's Law**, **Freundlich**, **Langmuir**, **Frumkin**, and **Temkin**.
   - Modeled adsorption energetics using the **Dubinin-Radushkevich (D-R)** equation to calculate mean free energy ($E$).

3. **Error Function Evaluation:**
   - Compared experimental vs. model-predicted capacities using non-linear $R^2$, Sum of Squared Errors (SSE), Chi-Square ($\chi^2$), and Root Mean Squared Error (RMSE) to avoid relying solely on linear regression coefficients.

---

## Regression & Error Analysis Summary

| Model | Linear Form / Trendline | Key Parameters | Linear $R^2$ | Non-Linear $R^2$ | SSE | $\chi^2$ | RMSE |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **Temkin** | $q_e = 25.93\ln(c_e) + 122.4$ | $A_T = 112.21\text{ L/g}$, $B_T = 0.223$ | **0.9972** | **0.9972** | **6.73** | **0.2429** | **1.497** |
| **Langmuir** | $\frac{c_e}{q_e} = 0.0086c_e + 0.0007$ | $q_{\max} = 116.28\text{ mg/g}$, $K_L = 12.29\text{ L/g}$ | 0.9786 | 0.9870 | 31.47 | 1.0059 | 3.239 |
| **Freundlich** | $\ln(q_e) = 0.6037\ln(c_e) + 5.4729$ | $K_F = 238.15$, $N = 1.656$ | 0.9353 | 0.9264 | 178.15 | 3.5000 | 7.706 |
| **Henry's Law** | $q_e = 315.58c_e + 23.183$ | $K_H = 315.58\text{ L/g}$ | 0.8881 | 0.8881 | 270.87 | 4.2097 | 9.502 |
| **Frumkin** | $\ln[\theta/((1-\theta)c_e)] = 0.1083\theta + 2.3982$ | $K_{FG} = 11.00$ | 0.0341 | — | — | — | — |

---

## Core Findings

- **Governing Isotherm:** The **Temkin model** provided the closest agreement across every evaluated metric ($R^2 = 0.9972$, lowest SSE and $\chi^2$)[cite: 10, 44, 45]. This points to an energetically heterogeneous surface where the heat of adsorption drops linearly as coverage increases[cite: 10, 45].
- **Adsorption Mechanism:** The Dubinin-Radushkevich mean free energy evaluated to **$E = 5.0\text{ kJ/mol}$**[cite: 10, 41]. Since $E < 8.0\text{ kJ/mol}$, the removal is driven by physical adsorption (physisorption) governed by weak Van der Waals interactions[cite: 10, 26].
- **Prototype Batch Reactor Sizing:** Sizing a single-stage batch reactor for 10 L of wastewater with an initial concentration of $2.5\text{ g/L}$ to achieve 90% dye removal ($c_e = 0.25\text{ g/L}$) yields an equilibrium capacity of $q_e = 86.45\text{ mg/g}$ via Temkin, requiring **$0.26\text{ kg}$** of activated carbon[cite: 10].

---

## Files
- `Adsorption_Isotherm_Regression_Analysis.xlsx`: Full calculation sheet, raw data, calibration plots, isotherm regressions, and error formulas.
