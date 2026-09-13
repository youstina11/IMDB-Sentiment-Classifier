# IMDB Sentiment Classifier

### Binary Sentiment Classification with Logistic Regression

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR-USERNAME/imdb-sentiment-classifier/blob/main/notebooks/IMDB_Logistic_Regression.ipynb)

![Project cover](images/cover.jpg)

## Description

An end-to-end binary sentiment classifier for the IMDB 50K movie reviews dataset. Raw review text is transformed into Bag-of-Words features and classified using a Logistic Regression model trained by minimizing Binary Cross-Entropy loss. The project covers preprocessing, mathematical derivations, model training with convergence analysis, full evaluation (accuracy, precision, recall, F1, ROC-AUC, threshold tuning, error analysis), model interpretability (top predictive words), a reusable inference function, and an independent SQL-based verification layer — achieving **87.6% test accuracy** and **0.94 ROC-AUC**.

**بالعربي:** موديل تصنيف مشاعر ثنائي (إيجابي/سلبي) على 50 ألف ريفيو من IMDB، باستخدام Bag-of-Words وLogistic Regression مدرّب بخسارة Binary Cross-Entropy، ومزوّد بتحليل رياضي، تقييم كامل، تفسير للموديل، ودالة تنبؤ جاهزة، بالإضافة لطبقة تحقق بلغة SQL. حقق دقة 87.6% وROC-AUC يساوي 0.94.

## Pipeline

![Project pipeline](images/pipeline.png)

## Project Structure

```
imdb-sentiment-classifier/
├── notebooks/
│   └── IMDB_Logistic_Regression.ipynb   # full executed notebook (all 5 tasks)
├── reports/
│   └── Project_Report.docx              # written report with results & SQL analysis
├── images/
│   ├── cover.jpg
│   └── pipeline.png
├── data/
│   └── README.md                        # instructions to download the dataset
├── requirements.txt
├── LICENSE
└── README.md
```

> **Setup note:** after you push this repo, replace `YOUR-USERNAME` in the Colab link above with your actual GitHub username so it opens your copy of the notebook.

## Run in Google Colab

Colab doesn't have access to this repo's `data/` folder at runtime, so before running the notebook in Colab, upload `IMDB_Dataset.csv` (see [`data/README.md`](data/README.md)) using the Colab file browser, or add a cell at the top with:
```python
from google.colab import files
files.upload()  # select IMDB_Dataset.csv
```

## Getting Started

```bash
git clone https://github.com/<your-username>/imdb-sentiment-classifier.git
cd imdb-sentiment-classifier
pip install -r requirements.txt
```

Download the dataset as described in [`data/README.md`](data/README.md), then run:

```bash
jupyter notebook notebooks/IMDB_Logistic_Regression.ipynb
```

## Key Results

| Metric | Value |
|---|---|
| Accuracy | 87.62% |
| Precision | 87.44% |
| Recall | 87.86% |
| F1-Score | 87.65% |
| ROC-AUC | 0.9410 |
| Test BCE (Log Loss) | 0.3993 |

**Algorithm:** Logistic Regression &nbsp;|&nbsp; **Dataset:** IMDB (50K Reviews) &nbsp;|&nbsp; **Loss:** Binary Cross-Entropy &nbsp;|&nbsp; **Framework:** Scikit-Learn &nbsp;|&nbsp; **Seed:** 42

## What's Inside the Notebook

1. **Preprocessing & Bag-of-Words** — text cleaning, 10,000-word `CountVectorizer` features
2. **Mathematical derivations** — logit, sigmoid, BCE loss, and why BCE beats MSE for logistic regression
3. **Training** — 80/20 stratified split (seed=42), `LogisticRegression(solver='lbfgs')`, loss convergence plot
4. **Evaluation** — accuracy/precision/recall/F1/ROC-AUC, confusion matrix, threshold experiment, error analysis
5. **Interpretability** — top positive/negative words, `predict_sentiment()` inference function
6. **Bonus: SQL verification** — the full test-set predictions are loaded into SQLite and the same metrics are recomputed with pure SQL as an independent cross-check

## License

This project is licensed under the [MIT License](LICENSE).
