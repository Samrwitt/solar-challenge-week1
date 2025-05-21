# Solar Farm Analysis — West Africa

A cross-country exploratory data analysis of solar farm measurements from Benin, Sierra Leone and Togo.  
This repository contains all code, data cleanup artifacts and visualizations for:

- **Task 1: Git & Environment Setup**  
- **Task 2: Data Profiling, Cleaning & EDA**  
- Task 3: Cross-Country Comparison  

> Optional Streamlit dashboard has not been implemented.

---

## 📋 Table of Contents

1. Project Overview  
2. Repository Structure  
3. Getting Started  
   - Prerequisites  
   - Installation  
4. Usage  
   - Task 1: Verify CI  
   - Task 2: Run EDA Notebooks  
   - Task 3: Run Cross-Country Comparison  
5. Data Description  
6. Branching Strategy  
7. Future Work  
8. License  

---

## Project Overview

MoonLight Energy Solutions is evaluating solar potential across three West African sites.  
This project delivers:

- A reproducible Git & CI/CD setup (Task 1)  
- Cleaned, profiled datasets and deep dives into each site’s solar, meteorological and maintenance data (Task 2)  
- Side-by-side statistical comparisons and visualizations to highlight relative performance (Task 3)  

---

##  Repository Structure

├── .github/
│   └── workflows/
│       └── ci.yml            # Continuous Integration: installs deps & runs basic checks
├── data/                     # Original CSVs (not committed)
├── notebooks/
│   ├── benin\_eda.ipynb       # Task 2 EDA for Benin
│   ├── sl\_eda.ipynb          # Task 2 EDA for Sierra Leone
│   ├── togo\_eda.ipynb        # Task 2 EDA for Togo
│   └── compare\_countries.ipynb  # Task 3: cross-country analysis
├── requirements.txt          # Python dependencies
├── .gitignore
└── README.md                 # This file


---

##  Getting Started

### Prerequisites

- **Python 3.8+**  
- **Git**  
- **Jupyter Notebook** or **JupyterLab**  

We recommend using **conda** for environment management.

### Installation

1. **Clone the repo**  
   ```bash
   git clone https://github.com/Samrwitt/solar-challenge-week1
   cd solar-challenge

2. Create & activate environment

      conda create --name solar-env python=3.9
   conda activate solar-env
   
3. Install dependencies

      pip install -r requirements.txt
   

---

##  Usage

### Task 1: Verify CI

* Commit to any branch and push — the GitHub Actions workflow (`.github/workflows/ci.yml`) will install dependencies and run python --version.
* Check the Actions tab for success/failure.

### Task 2: Run EDA Notebooks

1. Launch Jupyter:

      jupyter lab  # or jupyter notebook
   
2. Open notebooks/benin_eda.ipynb, sl_eda.ipynb, and togo_eda.ipynb.
3. Execute all cells to reproduce the profiling, cleaning, and plots.

### Task 3: Run Cross-Country Comparison

1. With the same environment active, open:

      notebooks/compare_countries.ipynb
   
2. Execute all cells to generate:

   * Side-by-side boxplots of GHI, DNI, DHI
   * Summary statistics table
   * ANOVA & Kruskal–Wallis tests
   * Bar chart ranking average GHI

---

##  Data Description

Each cleaned CSV in data/ contains:

| Column                       | Description                            |
| ---------------------------- | -------------------------------------- |
| Timestamp                    | Observation timestamp (hourly)         |
| GHI                          | Global Horizontal Irradiance (W/m²)    |
| DNI                          | Direct Normal Irradiance (W/m²)        |
| DHI                          | Diffuse Horizontal Irradiance (W/m²)   |
| ModA/B                       | Module sensor readings (W/m²)          |
| Tamb                         | Ambient temperature (°C)               |
| RH                           | Relative humidity (%)                  |
| BP                           | Barometric pressure (hPa)              |
| Precip.                      | Precipitation rate (mm/min)            |
| WS,WSgust,WSstdev,WD,WDstdev | Wind speed & direction metrics         |
| Cleaning                     | Binary flag indicating cleaning events |
| TModA/B                      | Module temperatures (°C)               |

---

##  Branching Strategy

* `main` — contains production-ready notebooks & CI.
* `setup-task` — Task 1 environment & CI setup.
* `eda-benin`, `eda-sl`, `eda-togo` — Task 2 explorations.
* `compare-countries` — Task 3 cross-country analysis.

Use pull requests to merge feature branches into main.

---

##  Future Work

* Build an interactive Streamlit dashboard to visualize key metrics.
* Integrate cloud-cover and aerosol data for refined performance modeling.
* Automate daily data ingest and nightly report generation via CI.

---
