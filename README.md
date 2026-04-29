# 🌡️ Global Temperature Explorer

An interactive **Exploratory Data Analysis (EDA)** Streamlit app for the [Berkeley Earth Surface Temperature dataset](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data) — covering global, country, and city-level climate records from **1750 to 2015**.

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-1.32+-red?logo=streamlit)
![Plotly](https://img.shields.io/badge/Plotly-5.20+-purple?logo=plotly)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📸 App Preview

| Overview | Global Trends | World Map |
|----------|--------------|-----------|
| KPI metrics, dataset previews, missing-value audit | Annual trend + seasonal splits + monthly box-plots | Interactive city scatter map + country choropleth |

---

## 📂 Project Structure

```
fda/
├── datasets/               ← CSVs (not tracked — see below)
│   ├── GlobalTemperatures.csv
│   ├── GlobalLandTemperaturesByCountry.csv
│   ├── GlobalLandTemperaturesByMajorCity.csv
│   ├── GlobalLandTemperaturesByState.csv
│   └── GlobalLandTemperaturesByCity.csv
│
├── src/
│   ├── data_loader.py      ← CSV loading with path resolution & sampling
│   ├── preprocessing.py    ← Cleaning, feature engineering (dates, lat/lon, seasons)
│   ├── analysis.py         ← EDA functions (trends, warming, distributions)
│   └── visualization.py    ← Dark-themed Plotly chart library
│
├── app/
│   ├── app.py              ← Main multi-page Streamlit app
│   └── components.py       ← Reusable UI (CSS, hero banner, sidebar, metrics)
│
├── notebooks/
│   └── analysis.ipynb      ← Full EDA notebook (46 cells, matplotlib + plotly)
│
├── scripts/
│   └── generate_notebook.py
│
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/<your-username>/global-temperature-explorer.git
cd global-temperature-explorer
```

### 2. Download the datasets

The CSV files are **not** included (largest file is ~508 MB). Download them from Kaggle:

👉 [Berkeley Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)

Place all 5 CSVs inside the `datasets/` folder.

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit app

```bash
python3 -m streamlit run app/app.py
```

Open [http://localhost:8501](http://localhost:8501) in your browser.

---

## 📊 App Pages

| Page | Features |
|------|----------|
| **🏠 Overview** | Dataset shapes, date range, KPI metrics, data previews, missing-value audit, descriptive stats |
| **📊 Global Trends** | Year-range slider, annual trend + 10-yr rolling avg, seasonal splits, monthly box-plots, correlation heatmap |
| **🌏 Country Analysis** | Top warming countries, single-country deep-dive (trend + monthly profile), world choropleth |
| **🏙️ City Analysis** | Hottest/coldest city rankings, city trend, monthly distribution |
| **📦 Distributions** | Histograms with mean line, per-dataset comparison, descriptive stats |
| **🗺️ World Map** | Interactive city scatter map coloured by temperature, country choropleth |

---

## 📓 Jupyter Notebook

The `notebooks/analysis.ipynb` covers the same EDA in a reproducible notebook format with both **matplotlib/seaborn** and **Plotly** charts:

- Missing value audit
- Global temperature trend (1750–2015)
- Seasonal & monthly patterns
- Country-level warming analysis (pre vs post 1950)
- City rankings (hottest/coldest)
- US state-level patterns
- Decade-level aggregation
- Key takeaways table

Run from the `notebooks/` directory or set the Jupyter kernel's working directory to the project root.

---

## 🛠️ Tech Stack

- **Python 3.9+**
- [Streamlit](https://streamlit.io) — web app framework
- [Plotly](https://plotly.com/python/) — interactive charts & maps
- [Pandas](https://pandas.pydata.org) — data manipulation
- [NumPy](https://numpy.org) — numerical computing
- [Seaborn](https://seaborn.pydata.org) — notebook static charts
- [Matplotlib](https://matplotlib.org) — notebook static charts

---

## 📄 License

MIT © Adhira Sethi
