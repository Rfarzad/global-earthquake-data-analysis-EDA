# 🌎 Global Earthquake Data Analysis (1985–2025)
This project performs an **Exploratory Data Analysis (EDA)** of nearly 20,000 earthquakes (magnitude ≥ 5.5) recorded globally from **1985 to 2025** using the **USGS ComCat** catalog.  
It demonstrates a reproducible Python workflow for **data cleaning**, **feature transformation**, and **visualization** to explore temporal, spatial, and statistical patterns in seismic activity.

---

## 📊 Objectives
1. **Depth–Magnitude Relationship:**  
   Examine how depth and magnitude are distributed and whether they are correlated.

2. **Temporal Behavior:**  
   Analyze annual earthquake frequencies and investigate how key statistics evolve over time.

3. **Geospatial Patterns:**  
   Map large and deep events to identify global seismic hotspots.

---

## 🧩 Dataset
- **Source:** [USGS Earthquake Catalog (ComCat)](https://earthquake.usgs.gov/data/comcat/)
- **Time span:** 1985.09.02 – 2025.09.02  
- **Scope:** ~19,600 events, magnitudes ≥ 5.5  
- **Key columns used:**  
  `time`, `latitude`, `longitude`, `depth`, `mag`, `magType`, `depthError`, `magError`, `id`

---

## 🧹 Data Cleaning & Preprocessing
- Handled missingness in `depthError` (~60%) and `magError` (~79%)  
- Replaced five negative depths with `0.0 km` (very shallow events)  
- Removed outliers based on |z| > 3 for uncertainty fields (<0.1% of total)  
- Encoded `magType` as a numeric variable (`magTypeNum`)  
- Extracted temporal fields (`year`, `month`, `day`) from timestamps  
- Final EDA table: **19,545 rows × 10 columns**

---

## 📈 Key Findings
- **Depth:** 80% of earthquakes occur at depths < 70 km; only ~6% are deeper than 300 km.  
- **Magnitude:** Strong right-skew; most events between 5.5–6.0, few > 8.0.  
- **Correlation:** Depth and magnitude show no strong relationship.  
- **Temporal stability:** Annual frequency stable (~450–550 events per year).  
- **Spatial distribution:** Strongest events occur in South/East Asia, South Australia, and along the western edges of North and South America.

---

## 🗺️ Visualizations
Includes:
- KDE and scatter plots for **depth vs. magnitude**  
- **Yearly frequency** trends over 40 years  
- **Interactive global maps** for depth and magnitude distributions  
  (implemented using `plotly` and `geopandas`)

---

## 🧠 Methods & Tools
| Category | Libraries Used |
|-----------|----------------|
| Data Handling | `pandas`, `numpy` |
| Visualization | `matplotlib`, `seaborn`, `plotly`, `geopandas` |
| Statistics | `scipy`, `statsmodels` |
| Cleaning & Export | `datetime`, `os`, `pathlib` |

---

## ⚙️ How to Reproduce
1. Download the data and notebook, and run the notebook when the data is in the same folder.
