*A companion repository for the article **“Prediction of depression risk based on AI art prompts”***  

- **Article:** <https://www.researchgate.net/publication/390458058_Prediction_of_depression_risk_based_on_AI_art_prompts>  
- **Dataset (OSF):** <https://osf.io/vpz6x/files/osfstorage>

---

## Overview

This repository provides a single, self-contained Python workflow that reproduces the:

- descriptive statistics  
- correlation analyses  
- group comparisons  
- basic regression models  
- classification models  

reported in the manuscript.

---

## Key Features

1. **Colab-ready, platform-agnostic**  
   Auto-mounts Google Drive when run in Colab; otherwise uses a local `BASE_DIR`.  

2. **Pre-aggregated input**  
   The CSV file contains one row per participant with prompt-level sentiment summaries (mean, SD, five-number summary).  

3. **Two clinically motivated cut-offs**  
   The columns `depression_group16` and `depression_group19` support both the *standard* (≥16) and *stricter* (≥19) thresholds of the 9-item Beck Depression Inventory.  

4. **Modular analysis pipelines**  
   - *Exploratory statistics* – histograms, power checks, gender × risk tables  
   - *Correlation pipeline* – Pearson *r*, bootstrap CIs, scatterplots, publication-quality *p*-value barplots (Excel export)  
   - *Group comparisons* – *t*-tests with effect-size shading, boxplots, sentiment-ratio pie charts  
   - *Predictive modelling* – VIF-filtered OLS and a robust GLM variant  
   - *Machine-learning classification* – baseline models with **hyperparameter tuning** and threshold optimisation  

---

## Dependencies

| Category            | Packages                                                                           |
|---------------------|------------------------------------------------------------------------------------|
| Core stack          | `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`                 |
| Jupyter / Colab     | `tqdm`, `os`, `google.colab` (only used when run in Colab)                         |
| Machine learning    | `scikit-learn`, `imbalanced-learn` (SMOTE, ensemble classifiers)                   |
| Optional (exports)  | `openpyxl` – for Excel output                                                      |

> **Python ≥ 3.10** recommended.

---

## Directory Layout

```text
.
├── analysis.py             # ← script / notebook exported as .py
├── aggregated_prompts.csv  # one row per participant (not included here)
├── figures/                # auto-generated on first run
└── excel/                  # auto-generated on first run

 Licence
 -------
 MIT Licence for the code; the anonymised prompt-level dataset is released
 under CC-BY-4.0 as detailed in the OSF record cited in the article.

 Citing
 ------
 If you build on this pipeline, please cite the original paper:

 Kellerwessel, K. (2024). *Prediction of depression risk based on AI art
 prompts.* Unpublished manuscript.  DOI: 10.21203/rs.3.rs-5578681/v1

 Contributions & Issues
 ----------------------
 Pull requests are welcome for bug-fixes or generalisation to other
 psychological constructs (e.g., Big Five traits).  
 If you have any questions, I'm ready to answer: **kellerwesselklaus @ gmail.com**. 

 Happy analysing!
----------------------------------------------------------------------------
