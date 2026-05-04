# Employment Protection Legislation and Total Factor Productivity
### Evidence from a Cross-Country OECD Panel Analysis (1998–2019)

**Author:** Aubin Espinas  
**Institution:** University of Caen Normandy — Master in Advanced Applied Economics  
**Course:** Project in Econometrics | Academic year 2025–2026

---

## Overview

This project investigates the impact of Employment Protection Legislation (EPL) on Total Factor Productivity (TFP) using a panel of 33 OECD countries over the period 1998–2019.

The analysis is conducted in R using a **Two-Way Fixed Effects (TWFE)** model with country-clustered standard errors, estimated via the `fixest` package. The full project is written as a **reproducible Quarto document** (`.qmd`), combining academic text, data analysis, and visualizations in a single file.

---

## Research Question

> Does tighter labor market regulation, as measured by the OECD EPL index, significantly affect productive efficiency in advanced economies?

---

## Methods

- Panel data: 33 OECD countries, 1998–2019 (726 observations)
- Dependent variable: TFP from Penn World Tables (normalized at 1 in 2021)
- Main variable of interest: OECD EPL Index (0–6 scale)
- Estimator: Two-Way Fixed Effects (country + year)
- Standard errors: clustered at country level
- Robustness checks: ALMP spending, log(public consumption), log(TFP), Mundlak-CRE model

**Econometric tests performed:**
- Breusch-Godfrey (serial autocorrelation)
- Breusch-Pagan & F-test (individual effects)
- Hausman test (FE vs RE)
- Wooldridge test (serial autocorrelation on residuals)
- Strict exogeneity test (lead EPL)

---

## Main Result

The EPL coefficient is positive but statistically non-significant (β = 0.010, p = 0.364) across all specifications. This **null finding** is consistent with the identification limits of macroeconomic panel data: low within-country variance of the EPL index and aggregation of heterogeneous sectoral effects.

---

## Repository Structure

```
epl-tfp-oecd-panel/
├── Project_Econometrics.qmd    # Full reproducible analysis (R + Quarto)
├── Project_in_Econometrics.pdf # Final rendered report
├── data/
│   └── sources.md              # Data sources and download links
└── .gitignore
```

---

## How to Reproduce

1. Install [R](https://www.r-project.org/) and [Quarto](https://quarto.org/)
2. Install the required R packages:
```r
install.packages(c("fixest", "plm", "tidyverse", "ggplot2", "knitr", "modelsummary"))
```
3. Download the data from the sources listed in `data/sources.md`
4. Place the files in the `data/` folder
5. Run:
```bash
quarto render Project_Econometrics.qmd
```

---

## Data Sources

See [`data/sources.md`](data/sources.md) for all download links.

| Source | Variable(s) |
|---|---|
| Penn World Tables (PWT 10.0) | TFP, Human Capital |
| OECD EPL Database | Employment Protection Index |
| OECD Economic Outlook | Output Gap |
| OECD Tax-Benefit Database | Net Replacement Rate |
| OECD — ALMP Spending | Active Labour Market Policies |
| EU KLEMS | Labour Productivity Growth |
| World Bank WDI | Trade, Unemployment, Inflation, GDPPC, GFCF |

---

## Key References

- Bassanini, Nunziata & Venn (2009) — *Economic Policy*
- Conti & Sulis (2016) — *Journal of Comparative Economics*
- Ciminelli & Franco (2025) — *OECD Productivity Working Papers*
- Feenstra, Inklaar & Timmer (2015) — *American Economic Review*
