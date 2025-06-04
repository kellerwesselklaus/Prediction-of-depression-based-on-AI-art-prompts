# ----------------------------------------------------------------------------
# Title:  AI-Assisted Self-Image Analysis for Depression-Risk Research
# ----------------------------------------------------------------------------
#
# Overview
# ========
# This repository accompanies the article
# **“Prediction of depression risk based on AI art prompts ”**
# It contains a single, self-contained Python workflow that reproduces the
# descriptive statistics, correlation analyses, group comparisons, basic
# regression models and classification models reported in the manuscript.

# The article is available here: 
# https://www.researchgate.net/publication/390458058_Prediction_of_depression_risk_based_on_AI_art_prompts
# And the database here: 
# https://osf.io/vpz6x/files/osfstorage
#
# Key Features
# ------------
# 1. **Colab-ready, but platform-agnostic**
#    If the notebook runs inside *Google Colab*, it auto-mounts Drive; otherwise
#    it treats `BASE_DIR` as a local path. 
#
# 2. **Pre-aggregated input**
#    The CSV already stores one row per participant with prompt-level sentiment
#    distributions (mean, SD, five-number summary) so the workflow stays light.
#
# 3. **Two clinically motivated cut-offs**
#    The columns `depression_group16` and `depression_group19` let you
#    replicate both the *standard* (≥16) and *stricter* (≥19) thresholds of
#    the 9-item Beck Depression Inventory in a single run.
#
# 4. **Modular analysis pipelines**
#    * **Exploratory statistics** – histograms, power calculation, gender × risk
#      contingency tables.
#    * **Correlation pipeline** – Pearson r, bootstrap CIs, scatterplots,
#      publication-quality p-value barplots; results exported to .xlsx.
#    * **Group-comparison pipeline** – t-tests (with effect-size shading),
#      boxplots, sentiment-ratio pie charts.
#    * **Predictive modelling** – VIF-filtered OLS and a robust GLM variant.
#    * **Machine learning classificiation** – Several basic ML models are employed - with hiperparameter-tuning and threshold-optimisation.
#
## Dependencies
#------------
#Python ≥3.10
#
#Core stack:
#- `numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`
#
#Jupyter/Colab:
#- `tqdm`, `os`, `google.colab` (auto-mount if run in Colab)
#
#Machine learning:
#- `scikit-learn` (models, metrics, pipelines)
#- `imbalanced-learn` (SMOTE, ensembles: `imblearn.*`)
#
#Optional:
#- `openpyxl` (for Excel export, if used in the notebook)
#
# Directory Layout
# ----------------
# .
# ├── analysis.py             # <-- the script / notebook exported as .py
# ├── aggregated_prompts.csv  # one row per participant (not included here)
# ├── /figures                # auto-generated on first run
# └── /excel                  # auto-generated on first run
#
# Licence
# -------
# MIT Licence for the code; the anonymised prompt-level dataset is released
# under CC-BY-4.0 as detailed in the OSF record cited in the article.
#
# Citing
# ------
# If you build on this pipeline, please cite the original paper:
#
# Kellerwessel, K. (2024). *Prediction of depression risk based on AI art
# prompts.* Unpublished manuscript.  DOI: 10.21203/rs.3.rs-5578681/v1
#
# Contributions & Issues
# ----------------------
# Pull requests are welcome for bug-fixes or generalisation to other
# psychological constructs (e.g., Big Five traits).  
# If you have any questions, I'm ready to answer: **kellerwesselklaus @ gmail.com**. 
#
# Happy analysing!
# ----------------------------------------------------------------------------
