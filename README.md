# Corporate Risk-Governance Narrative Disclosure Analysis (2020–2025)

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An empirical quantitative research study investigating the relationships between **Risk-Governance Disclosure Frequency** (`Risk_Governance_Score`), **Report Readability** (`Readability_Score` / `Flesch_Reading_Ease` & `Fog_Index`), and **Narrative Sentiment** (`Net_Sentiment` / `Sentiment_Score`) across 72 company-year annual reports (12 multinational corporations in Banking, Energy, and Manufacturing, 2020–2025).

---

## 📌 Research Hypotheses & Framework

- **H1 (Multiple Linear Regression)**: Higher frequency of risk-governance information disclosed (`Risk_Governance_Score`) significantly predicts increased annual-report readability and net narrative sentiment, controlling for report length (`Disclosure_Length_Words`), sector, and year.
- **H2 (Industry Comparison)**: Statistically significant variations exist in readability and sentiment scores between Banking, Energy, and Manufacturing companies.
- **H3 (Longitudinal Trend)**: Statistically significant longitudinal variation and upward trends occurred across 2020–2025 in disclosure frequency, readability, and net sentiment.

---

## 📁 Repository Structure

```
.
├── roshan_risk_governance_analysis.ipynb   # Main interactive Jupyter Notebook (Pre-executed with all figures & tables)
├── run_analysis.py                        # Standalone modular Python analysis script
├── README.md                              # Repository documentation
├── figures/                               # High-resolution (300 DPI) publication-quality charts
│   ├── dist_boxplot_*.png                 # Histograms & Boxplots with annotated outliers
│   ├── correlation_heatmaps.png           # Pearson & Spearman correlation heatmaps
│   ├── industry_comparison_*.png          # Sector comparison boxplots (H2 testing)
│   ├── year_trend_*.png                   # 2020–2025 longitudinal trend lines (H3 testing)
│   └── regression_diagnostics_4panel.png  # 4-panel regression diagnostic suite
└── tables/                                # Formatted CSV & Excel data output tables
    ├── descriptive_statistics.xlsx        # Summary statistics & outlier counts
    ├── pearson_correlation_r.xlsx         # Pearson linear correlation matrix & p-values
    ├── spearman_correlation_r.xlsx        # Spearman rank correlation matrix (robustness check)
    ├── anova_industry_h2_results.xlsx     # Levene's test, 1-way ANOVA & Welch ANOVA
    ├── tukey_posthoc_*.txt                # Tukey HSD pairwise post-hoc test results
    ├── year_trend_h3_results.xlsx         # Year trend regression slopes & ANOVA
    ├── regression_coefficients_h1.xlsx    # Multiple linear regression coefficients & 95% CIs
    ├── regression_fit_statistics_h1.xlsx  # R^2, Adjusted R^2, and F-statistics
    ├── regression_diagnostics_summary.xlsx# Linearity, Normality, Homoscedasticity tests
    ├── vif_multicollinearity.csv          # Variance Inflation Factors (VIF)
    └── sensitivity_fog_index_coefficients.xlsx # Robustness model using Gunning Fog Index
```

---

## 🛠️ Installation & Requirements

Ensure Python 3.9+ is installed along with the necessary scientific and plotting dependencies:

```bash
pip install pandas numpy scipy statsmodels matplotlib seaborn openpyxl ipykernel
```

---

## 🚀 How to Run

### Option 1: Jupyter Notebook (Recommended)
Launch Jupyter Notebook or Jupyter Lab and open `roshan_risk_governance_analysis.ipynb`:

```bash
jupyter notebook roshan_risk_governance_analysis.ipynb
```
*Note: All cells are pre-executed with interactive outputs, markdown explanations, and plots embedded.*

### Option 2: Python Command Line
Run the master python script from your terminal:

```bash
python run_analysis.py
```
*All output charts and tables will automatically refresh in `figures/` and `tables/`.*

---

## 📊 Summary of Key Empirical Findings

| Hypothesis | Analytical Test Method | Empirical Result | Status |
| :--- | :--- | :--- | :---: |
| **H1 (Readability Model)** | Multiple Linear Regression | $R^2 = 0.7100, F(5, 66) = 32.32, p < 0.0001$. Industry fixed effects and positive time trend drive readability. | **SUPPORTED** |
| **H1 (Sentiment Model)** | Multiple Linear Regression | $R^2 = 0.8658, F(5, 66) = 85.19, p < 0.0001$. Risk governance frequency ($\beta = -0.0012, p = 0.012$) predicts cautious tone. | **SUPPORTED** |
| **H2 (Industry Variations)** | Levene's Test + 1-Way ANOVA / Welch ANOVA | $p < 0.0001$ across all variables. Manufacturing reports are most readable; Banking disclosures are dense with high governance frequency. | **SUPPORTED** |
| **H3 (Longitudinal Trend)** | Categorical ANOVA + Trend Regression | Readability ($\beta_{\text{trend}} = +0.4849, p = 0.0003$) and Net Sentiment ($\beta_{\text{trend}} = +0.0006, p < 0.0001$) improved significantly over 2020–2025. | **SUPPORTED** |
| **Diagnostics & Sensitivity** | RESET, Shapiro-Wilk, Breusch-Pagan, VIF, Fog Index | Linearity, residual normality, and homoscedasticity satisfied. Results hold across Gunning Fog Index formula check. | **ROBUST** |

---

## 📜 Citation & License

This repository is distributed under the **MIT License**.
