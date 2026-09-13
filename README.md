# Data

This project uses the **IMDB Dataset of 50K Movie Reviews**.

The raw CSV is not committed to this repository (66 MB — kept out of git on purpose).
To reproduce the notebook:

1. Download `IMDB Dataset.csv` from Kaggle: https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
2. Place it in this `data/` folder as `IMDB_Dataset.csv`
3. Run `notebooks/IMDB_Logistic_Regression.ipynb` top to bottom

Expected shape: `(50000, 2)` with columns `review` and `sentiment`, perfectly balanced
(25,000 positive / 25,000 negative).
