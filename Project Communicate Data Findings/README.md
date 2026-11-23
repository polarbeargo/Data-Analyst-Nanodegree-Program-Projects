# Communicate Data Findings: Ford GoBike

## Overview

This project explores February 2019 Bay Wheels (formerly Ford GoBike) bike-share trips and communicates selected findings in a separate explanatory presentation. It examines trip duration, rider type, usage timing, and rider age.

## Files

- [Part I: exploratory notebook](Part_I_exploration_template.ipynb) and [HTML report](Part_I_exploration_template.html)
- [Part II: explanatory notebook](Part_II_explanatory_template.ipynb) and [HTML report](Part_II_explanatory_template.html)
- [February 2019 trip data](201902-fordgobike-tripdata.csv)

## Approach and findings

The exploration parses timestamps, derives trip duration in minutes and usage-time features, and limits age-based analysis to plausible ages. It investigates the distribution of trip durations and compares rider types across times and age groups. The explanatory notebook presents a subset of those findings with focused visuals.

- Trip durations are right-skewed; most rides are short.
- Subscribers account for most trips and generally take shorter rides than Customers.
- Subscriber use is concentrated on weekdays and around commute hours; the observed age-duration relationship is comparatively modest.

These are patterns in one month of trips, not evidence that rider type or age causes a particular trip duration. Some demographics are missing, and age-based comparisons use only riders with plausible recorded birth years.

## Run the notebooks

Install Python 3, Jupyter, NumPy, pandas, matplotlib, and seaborn. From this directory, open Jupyter:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn
jupyter notebook
```

Open each notebook and run its cells from top to bottom. Keep the CSV in this directory: both notebooks read it relative to the current working directory. The HTML reports can be opened in a browser without running the notebooks.
