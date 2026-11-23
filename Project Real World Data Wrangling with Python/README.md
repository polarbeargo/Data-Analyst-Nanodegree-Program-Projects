# Real World Data Wrangling: GDP Growth and Equity Prices

## Overview

This project asks how annual real GDP growth is associated with same-year equity-index price changes across reporting economies from 2000 to 2023. It combines World Bank indicators by economy code and year, assesses and cleans the data, and answers the question with two visualizations.

## Files

- [Executed notebook](<World Bank GDP and Equity/Data_Wrangling_World_Bank.ipynb>)
- [Raw GDP bulk CSV archive](<World Bank GDP and Equity/raw/world_bank_gdp_growth_bulk_csv.zip>)
- [Raw equity API responses](<World Bank GDP and Equity/raw/world_bank_equity_index_api_pages.json>)
- [Combined cleaned dataset](<World Bank GDP and Equity/cleaned/gdp_growth_and_equity_index_country_year_2000_2023.csv>)
- [Submission ZIP](World_Bank_GDP_Equity_Submission.zip)

## Sources and methods

1. [GDP growth (annual %)](https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG), indicator `NY.GDP.MKTP.KD.ZG`, is gathered by programmatically downloading a World Bank bulk CSV archive. Each country-year value is an observation, even though the original file places years in separate columns.
2. [S&P Global Equity Indices (annual % change)](https://data.worldbank.org/indicator/CM.MKT.INDX.ZG), indicator `CM.MKT.INDX.ZG`, is gathered from the World Bank Indicators API as paginated JSON. It measures US-dollar stock-index price changes, not total returns.

The notebook inspects missing country codes and indicator values, reshapes GDP year columns, and extracts nested API country names. It excludes missing join keys and incomplete observations, restricts the analysis to individual economies using World Bank metadata, and performs a validated one-to-one country-year join. Raw files are retained separately from the cleaned CSV.

## Findings and limitations

The bundled data produces 1,893 matched country-year observations across 84 economies. The pooled Pearson correlation between GDP growth and equity-index price change is approximately **0.073**, a weak positive association. The sample covers only economies with both indicators available; exchange rates, repeated observations, global shocks, and data revisions can affect the result. This descriptive comparison does not establish causation.

## Run the notebook

Install Python 3, Jupyter, NumPy, pandas, and matplotlib. Start Jupyter from the notebook's directory:

```bash
python -m pip install jupyter numpy pandas matplotlib
cd "World Bank GDP and Equity"
jupyter notebook
```

Open the notebook and run the cells in order. By default it reads the included raw files, so execution does not require network access. Set `REFRESH_RAW = True` to download current World Bank data; this requires internet access, replaces the local raw snapshots, and may change the results. The notebook writes the combined CSV to `cleaned/`.
