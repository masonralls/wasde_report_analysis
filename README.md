# WASDE Report Analysis

Exploratory analysis of USDA World Agricultural Supply and Demand Estimates (WASDE) report data, covering U.S. production and estimate trends across multiple commodities.

## Project Structure

```
wasde_analysis/
├── .venv/                  # Python virtual environment (not tracked)
├── data/
│   ├── raw/                # Original WASDE report exports
│   └── processed/          # Cleaned, analysis-ready CSVs
├── notebooks/
│   └── eda/                # Exploratory data analysis notebooks
├── .gitignore
├── requirements.txt
└── README.md
```

## Data

Data is sourced from public USDA WASDE reports and covers estimates for the following commodities:

- Corn
- Cotton
- Wheat (HRS, HRW)
- Oats
- Rice
- Soybeans (production, meal, oil)
- Sugar

Processed datasets include fields such as `ReleaseDate`, `Value`, `Unit`, along with commodity- and attribute-specific identifiers used to distinguish between different WASDE estimate series.

## Setup

**1. Clone the repository**
```bash
git clone https://github.com/masonralls/wasde_report_analysis.git
cd wasde_analysis
```

**2. Create and activate a virtual environment**
```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1      # Windows PowerShell
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

## Progress So Far

- [x] Initialized Git repository and connected to GitHub remote
- [x] Set up `.gitignore` to exclude environment files, notebook checkpoints, and cache
- [x] Created and activated a Python virtual environment (`.venv`)
- [x] Established `requirements.txt` for reproducible environment setup
- [x] Loaded and organized raw commodity CSVs (corn, cotton, wheat, oats, rice, soybeans, sugar) into `data/`
- [x] Built initial EDA notebook (`wasde_eda.ipynb`) to explore U.S. production and estimate data
- [x] Cleaned and converted `ReleaseDate` fields to proper datetime format for time series plotting
- [x] Generated full time series plots of estimates by commodity and attribute over time

## Next Steps

- [ ] Reimport and refresh raw data files from local source
- [ ] Expand EDA to compare estimates across commodities
- [ ] Add year-over-year and month-over-month comparison views
- [ ] Document data source and last-updated date for each dataset
- [ ] Explore forecasting or trend analysis on selected commodities

## Notes

- Public WASDE data is committed directly to the repository for reproducibility.
- Large or non-public files remain excluded via `.gitignore`.
