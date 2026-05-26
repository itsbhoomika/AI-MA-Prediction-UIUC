# AI-Driven M&A Outcome Prediction

> **93% accuracy** predicting merger & acquisition outcomes by fusing structured financial ratios with unstructured market news — built at UIUC.

[![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org)

## Overview

Traditional M&A risk models rely solely on financial ratios, missing signals buried in news coverage. This project closes that gap by combining:

- **Structured data** — leverage ratios, EV/EBITDA, revenue growth, peer benchmarks
- **Unstructured data** — market news headlines processed via TF-IDF, Word2Vec, and FinBERT sentiment

The final ensemble achieves **93% accuracy**, demonstrating the value of multimodal feature fusion in investment banking analytics.

## File Guide

| File | What it does |
|------|--------------|
| `Text_Cleaning.ipynb` | Cleans and normalizes raw news headlines — stopword removal, lemmatization, deduplication |
| `Sentiment.ipynb` | Runs FinBERT on cleaned headlines to extract domain-specific financial sentiment scores |
| `Word2vec.ipynb` | Trains Word2Vec embeddings on the news corpus; produces dense vector representations per company |
| `Model_Numerical.ipynb` | Engineers financial ratios (leverage, valuation multiples, growth); trains and evaluates baseline ML models |
| `Final (1).ipynb` | **Master notebook** — merges numerical + text + sentiment features, tunes the ensemble, reports 93% accuracy |
| `Final_Model_application.ipynb` | Applies the trained model to new company pairs for real-world inference |
| `report/` | Full research report |

## Data Files

| File | Contents |
|------|----------|
| `headlines.xlsx` | Raw market news headlines per company |
| `target_data.xlsx` | Financial ratios for M&A target companies |
| `peer_data.xlsx` | Peer-group financial benchmarks |
| `all_data.xlsx` | Master merged dataset |
| `sentiment_finbert_Labs.xlsx` | FinBERT-generated sentiment scores |

## Tech Stack

`Python` · `Scikit-learn` · `XGBoost` · `Gensim (Word2Vec)` · `FinBERT` · `TF-IDF` · `Pandas` · `Matplotlib`

## Results

| Metric | Value |
|--------|-------|
| Accuracy | **93%** |
| Feature sources | Financial ratios + news embeddings + sentiment |
| Approach | Ensemble (XGBoost + Logistic Regression) |

## How to Run

```bash
# Run notebooks in order:
jupyter nbconvert --to notebook --execute Text_Cleaning.ipynb
jupyter nbconvert --to notebook --execute Sentiment.ipynb
jupyter nbconvert --to notebook --execute Word2vec.ipynb
jupyter nbconvert --to notebook --execute Model_Numerical.ipynb
jupyter nbconvert --to notebook --execute "Final (1).ipynb"
```

## Context

Research project at the **University of Illinois Urbana-Champaign**, targeting investment banking and financial analytics use cases.
