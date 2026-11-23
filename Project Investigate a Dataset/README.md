# Investigate a Dataset: TMDb Movies

## Overview

This project explores relationships between movie characteristics, audience ratings, and adjusted box office revenue. It asks which attributes are associated with higher ratings and which are associated with higher inflation-adjusted revenue.

## Files

- [Analysis notebook](Investigate_a_Dataset.ipynb)
- [HTML report](Investigate_a_Dataset.html)
- [TMDb movie dataset](Database_TMDb_movie_data/tmdb-movies.csv)

The folders for no-show appointments and NCIS/census data contain other datasets; they are not used in this notebook.

## Approach and findings

The notebook assesses and cleans the data, removes duplicates, selects relevant fields, and derives primary genre, decade, and return on investment. It uses distributions, group comparisons, correlations, visualizations, and a permutation test to explore the research questions.

- Popularity has a positive association with audience ratings, while runtime has a weaker relationship.
- Adjusted budget and adjusted revenue have a positive association, particularly in the log-scaled comparison.
- Average ratings differ across genres and median adjusted revenue varies across decades.

These are observational associations, not causal conclusions. Missing or zero financial values, the use of only the first listed genre, and uneven representation across groups can affect the results.

## Run the notebook

Install Python 3, Jupyter, NumPy, pandas, matplotlib, and seaborn. From this directory, start Jupyter:

```bash
python -m pip install jupyter numpy pandas matplotlib seaborn
jupyter notebook
```

Open the analysis notebook and run cells in order. It searches recursively from the current working directory for `tmdb-movies.csv`, so keep the dataset under this project directory. Alternatively, open the HTML report in a browser.
