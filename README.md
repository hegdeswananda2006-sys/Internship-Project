# Heart Disease Risk Analysis — Internship Project

> **Author:** Swananda Shridhar Hegde   
> **Dataset:** UCI Heart Disease (Cleveland)  
> **Stack:** Python · Pandas · Matplotlib · Seaborn · Plotly · Dash

---

## Overview

A complete end-to-end data analysis project on the **UCI Cleveland Heart Disease dataset** (303 patients, 14 features). The project covers:

- Data loading, cleaning, and descriptive statistics  
- Full Exploratory Data Analysis (EDA) with 8 publication-quality charts  
- An interactive **Plotly Dash dashboard** with filters and 4 themed tabs  
- A professional project report with embedded charts  

---

## Dataset

| Property | Value |
|---|---|
| Source | [UCI ML Repository — Heart Disease](https://archive.ics.uci.edu/ml/datasets/heart+disease) |
| File | `heart_disease_cleveland_cleaned.csv` |
| Rows | 303 |
| Features | 14 (13 predictors + 1 target) |
| Target | `0` = No Disease · `1` = Disease |

**Feature list:** `age`, `sex`, `cp`, `trestbps`, `chol`, `fbs`, `restecg`, `thalach`, `exang`, `oldpeak`, `slope`, `ca`, `thal`, `target`

---

## Project Files

```
heart_disease_project/
│
├── heart_disease_cleveland_cleaned.csv   ← Cleaned dataset
├── requirements.txt                      ← Python dependencies
│
├── Swananda_HeartDiseaseEDA.ipynb        ← Full EDA notebook (Jupyter)
├── app.py                                ← Plotly Dash interactive dashboard
│
├── Swananda_ProjectReport.docx           ← Project report with charts & insights
├── README.md                             ← This file
│
├── generate_screenshots.py               ← Script: generate EDA PNGs
├── generate_dashboard_screenshots.py     ← Script: generate dashboard PNGs
├── build_report.py                       ← Script: build the .docx report
│
└── screenshots/                          ← All generated chart images
    ├── 01_histograms.png
    ├── 02_barcharts_categorical.png
    ├── 03_target_distribution.png
    ├── 04_comparative_charts.png
    ├── 05_correlation_heatmap.png
    ├── 06_target_correlation_bar.png
    ├── 07_age_by_target.png
    └── 08_boxplots.png
```

---

## Technologies Used

| Library | Version | Purpose |
|---|---|---|
| pandas | 2.1.4 | Data loading, cleaning, analysis |
| numpy | 1.26.4 | Numerical operations |
| matplotlib | 3.8.4 | Static chart generation |
| seaborn | 0.13.2 | Statistical visualizations |
| plotly | 5.22.0 | Interactive charts |
| dash | 2.17.1 | Web dashboard framework |
| dash-bootstrap-components | 1.6.0 | Dashboard UI components |
| scikit-learn | 1.4.2 | (Available for ML extension) |
| openpyxl | 3.1.2 | Excel file reading |
| python-docx | 1.1.2 | Report generation |

---

## Setup Instructions

### 1. Clone / Download the project folder

```bash
cd heart_disease_project
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Jupyter Notebook (EDA)

```bash
jupyter notebook Swananda_HeartDiseaseEDA.ipynb
```

### 5. Launch the Dashboard

```bash
python app.py
```

Then open **http://127.0.0.1:8050** in your browser.

---

## Dashboard Usage

The dashboard has a **filter sidebar** and **4 tabs**:

### Sidebar Filters
| Filter | Description |
|---|---|
| Age Range | Slider to restrict patients by age (29–77) |
| Sex | Toggle Female (0) / Male (1) |
| Chest Pain Type | Multi-select chest pain categories |

All 4 KPI cards and all charts update reactively when filters change.

### Tabs

| Tab | Contents |
|---|---|
| **Demographics** | Age histogram, disease by sex, disease by age group, BP/cholesterol/HR distributions |
| **Clinical Features** | Grouped boxplots for continuous features; bar charts for all categorical features |
| **Target Analysis** | Donut chart, age vs max-HR scatter, 4 comparative grouped bars |
| **Correlation** | Full Pearson heatmap + horizontal feature-vs-target correlation bar chart |

### Colour Scheme

| Colour | Meaning |
|---|---|
| 🔵 Blue `#2563EB` | No Disease (0) |
| 🔴 Red `#DC2626` | Disease (1) |
| 🟢 Teal `#0D9488` | General categorical |
| 🟠 Orange `#EA580C` | Accent / secondary categorical |

---

## Key Insights

1. **Thalassemia (`thal`) is the strongest predictor** — reversible defect (thal=7) → ~88% disease rate. `|r| = 0.524`
2. **Major vessels (`ca`) shows monotonic risk increase** — from 27% disease at ca=0 to 91% at ca=3. `|r| = 0.460`
3. **Exercise angina (`exang`)** — patients with angina have 76% disease rate vs 31% without. `|r| = 0.432`
4. **Low max heart rate (`thalach`)** — disease patients average 138 bpm vs 158 bpm healthy. `r = −0.417`
5. **ST depression (`oldpeak`)** — median 1.5 in disease vs 0.0 in healthy patients. `|r| = 0.425`
6. **Asymptomatic chest pain** — highest absolute disease count despite lacking symptoms.
7. **Cholesterol and BP** — weak individual predictors (`|r| < 0.15`), but relevant in multivariate models.

---

## Generate Charts & Report (standalone)

```bash
# Regenerate all 8 EDA screenshots
python generate_screenshots.py

# Rebuild the Word report
python build_report.py
```

---

## License

This project is for educational/internship purposes.  
Dataset: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — UCI ML Repository.
