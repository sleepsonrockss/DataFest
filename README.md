# 🏥 DataFest — Medical Diagnosis Dataset Analysis

A data science competition project from **ASA DataFest**, where teams were given a real-world, anonymized medical dataset and challenged to extract meaningful insights within a limited timeframe. Our team performed end-to-end analysis covering data cleaning, augmentation, time series forecasting, visualization, and clinical inference — all presented to a panel of judges.

---

## 📋 Competition Overview

**ASA DataFest** is a nationally recognized data hackathon where students work in teams to analyze a complex, real-world dataset over 48 hours and deliver a compelling data-driven story to industry judges.

Our dataset consisted of **7 CSV files** representing a relational medical records system, covering patient demographics, clinical encounters, diagnoses, providers, departments, and social context.

---

## 📁 Dataset Files

| File | Description |
|------|-------------|
| `patients.csv` | Patient demographics and identifiers |
| `encounters.csv` | Clinical visit records and timestamps |
| `diagnosis.csv` | Diagnosis codes and descriptions per encounter |
| `departments.csv` | Hospital department metadata |
| `providers.csv` | Provider (clinician) information |
| `social_determinants.csv` | Social determinants of health (SDOH) per patient |
| `tigercensus codes.csv` | Geographic/census area codes for regional mapping |

> All datasets were anonymized and provided exclusively for competition use.

---

## 🔬 Project Pipeline

### 1. 🧹 Data Cleaning
- Handled missing values across all 7 CSVs using imputation strategies
- Standardized date formats and resolved inconsistencies in diagnosis codes (ICD-10)
- Deduplicated records and resolved foreign key mismatches across relational files
- Normalized categorical fields (department names, provider types, SDOH categories)

### 2. 📈 Data Augmentation
- Engineered new features from existing columns (e.g., patient age at encounter, time between visits, encounter frequency)
- Merged datasets across keys to build a unified analytical frame
- Mapped census codes to geographic metadata for regional analysis

### 3. ⏱️ Time Series Prediction (Missing Value Imputation)
- Applied time series forecasting to fill longitudinal gaps in encounter and diagnosis records
- Used temporal patterns in patient visit history to impute missing timestamps and forward-fill sparse diagnosis sequences
- Validated imputed values against known distributions to minimize introduced bias

### 4. 📊 Data Visualization
- Built charts and dashboards illustrating:
  - Diagnosis frequency distributions across departments and demographics
  - Encounter trends over time (seasonal patterns, visit volume)
  - Social determinants of health correlated with diagnosis outcomes
  - Provider workload and department utilization
  - Geographic heatmaps using census codes

### 5. 🧠 Inference & Insights
- Identified high-risk patient subgroups based on diagnosis patterns and SDOH indicators
- Surfaced under-served demographics with low encounter rates relative to diagnosis burden
- Correlated social determinants (housing, income, transportation) with diagnosis severity and re-admission rates
- Delivered actionable recommendations for resource allocation and preventive care targeting

---

## 🛠️ Tech Stack

| Tool | Use |
|------|-----|
| **Python** | Primary language |
| **Pandas** | Data cleaning, merging, transformation, and aggregation |
| **Matplotlib / Seaborn** | Static visualizations |
| **Jupyter Notebooks** | Exploratory data analysis and pipeline documentation |

---

## 📂 Repository Structure

```
DataFest/
│
├── data/                    # Raw CSV files (not included — competition data)
│
├── notebooks/
│   ├── 01_cleaning.ipynb    # Data cleaning and preprocessing
│   ├── 02_augmentation.ipynb # Feature engineering and dataset merging
│   ├── 03_timeseries.ipynb  # Time series imputation
│   └── 04_visualization.ipynb # Charts and inference
│
├── presentation/            # Slides used for judge presentation
│
├── requirements.txt
└── README.md
```

---

## 🚀 Running the Project

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/sleepsonrockss/DataFest.git
cd DataFest
pip install -r requirements.txt
```

### Running Notebooks

```bash
jupyter notebook
```

Open the notebooks in order (01 → 04) for the full pipeline.

> **Note:** The original competition CSVs are not included in this repository due to data use restrictions. The notebooks are structured so the pipeline and methodology are fully reproducible with any similarly structured medical dataset.

---

## 📌 Key Findings

- Patients with adverse social determinants (e.g., housing instability, low income) showed significantly higher rates of chronic condition diagnoses
- Certain departments were disproportionately overloaded relative to patient volume, suggesting staffing inefficiencies
- Time series gap-filling revealed that longitudinal patient records had systematic missingness — not random — indicating documentation gaps in specific provider cohorts
- Geographic clustering via census codes exposed regional disparities in encounter frequency and diagnosis access

---

## 👥 Team

Built during ASA DataFest by a team of data science students competing under time pressure with a dataset revealed only at the start of the competition.

---

## 📄 License

This repository contains only code and methodology — no patient data is included or will be shared. All analysis was conducted under the data use agreement provided by ASA DataFest organizers.
