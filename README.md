# Domestic Ideology and UN Alignment (1992–2020)
Directed Independent Research Project, CIEE Berlin, Fall 2025

---

## Overview
This project investigates whether **domestic political factors**, such as executive ideology, institutional checks, and election timing, can predict a country’s **foreign policy alignment** in the **United Nations General Assembly (UNGA)** from 1992 to 2020.  

A **Random Forest Regressor** is trained on a merged dataset combining domestic political indicators from the *Database of Political Institutions (DPI)* and ideal point estimates from the *UNGA Voting dataset*, both linked below.

The analysis evaluates which domestic features most influence international alignment and examines model biases over time and across countries.

---

## Objectives
- Load a preprocessed dataset containing:  
  - **Database of Political Institutions (DPI)** — Executive ideology, institutional checks, and election indicators  
  - **UNGA Ideal Points** — Quantified foreign policy alignment scores  
- Train a `RandomForestRegressor` to predict UNGA ideal points (`idealpointfp`)  
- Evaluate model performance (RMSE, R²) on test data (2016–2020)  
- Visualize feature importance and residual patterns by country and year  
- Interpret whether domestic ideology or institutional factors explain alignment trends

---

## Repository Contents
| File / Folder | Description |
|----------------|--------------|
| `/notebook/dir_un_alignment.ipynb` | Main Jupyter Notebook with analysis, figures, and discussion |
| `/data/dpi2020_mod.csv` | Preprocessed dataset combining DPI and UNGA data |
| `/data/` | Train/test splits and model outputs |
| `README.md` | Project overview and documentation |

---

## Key Findings
- **Temporal and institutional factors** (especially `year` and `checks`) explain more variance in UN alignment than short-term electoral variables.  
- **Ideology changes** (`ideology_changed`) have low predictive weight, implying that foreign policy continuity often persists across elections.  
- **Systematic residuals** show under-prediction for highly aligned states (e.g., United States, Poland) and over-prediction for less aligned states (e.g., India, Brazil).  
- Residuals increase after 2016, suggesting a **structural shift** in global alignment, possibly associated with the **rise of populist and nationalist governments** and renewed geopolitical polarization.

---

## Methodology Summary
- **Model:** Random Forest Regressor (`scikit-learn`)  
- **Training period:** 1992–2015  
- **Test period:** 2016–2020  
- **Features:**  
  - Executive ideology (`execrlc`)  
  - Institutional checks (`checks`)  
  - System type (`system`)  
  - Election timing and post-election effects (`years_since_elec`, `post_elec_1y–3y`)  
  - Year (`year`)  
- **Target:** `idealpointfp` (UNGA ideal point score)  

Residual plots and feature importances are used to interpret where and why the model succeeds or fails.

---

## Acknowledgments
This research was conducted as part of the **Directed Independent Research** course at the **Council on International Educational Exchange (CIEE)** program in Berlin, Germany.  
I would like to express my sincere gratitude to **Dr. Christian Achrainer** for his guidance, feedback, and continued support throughout this research process.

---

## References
Voeten, Erik. 2009. *[United Nations General Assembly Ideal Points](https://doi.org/10.7910/DVN/LEJUQZ).* Harvard Dataverse.  
Inter-American Development Bank (IDB). 2023. *[Database of Political Institutions (DPI)](https://www.iadb.org/en/knowledge-resources/research-idb/research-datasets/database-political-institutions).*
