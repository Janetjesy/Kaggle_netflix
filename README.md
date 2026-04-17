Netflix Data Analysis



Dataset

https://www.kaggle.com/code/jaycijanet/netflix


# 🎬 Streaming Shifts: Netflix Content Analysis & Recommendation Engine

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-orange)](https://pandas.pydata.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Scikit--Learn-green)](https://scikit-learn.org/)

## 📌 Project Overview
This project performs an end-to-end Exploratory Data Analysis (EDA) and builds a Content-Based Recommendation System using the Netflix Movies and TV Shows dataset. The goal is to move beyond simple observation and create a predictive tool that assists in content discovery.

## 🛠️ The "Safe Zone" Architecture
To maintain data integrity, the project implements a **Dual-DataFrame Strategy**:
- `df`: The raw, immutable dataset (The Original).
- `netflix_copy`: The "Sandbox" where all cleaning, feature engineering, and modeling take place.

## 🧹 Data Cleaning & Preparation
Before analysis, the data underwent a rigorous cleaning process:
- **Missing Value Mitigation:** Filled 2,634 missing Directors and ~800 missing Cast/Country entries with placeholders ("Unknown") to prevent data loss.
- **Structural Standardization:** Applied `.str.strip()` to all text columns to eliminate "silent" whitespace errors.
- **Type Conversion:** Converted `date_added` from strings to datetime objects for time-series analysis.
- **Outlier Handling:** Pruned the "Tiny Errors" (<10 rows) in ratings and duration to ensure 100% accuracy in visualizations.

## 🚀 Feature Engineering
I transformed raw text into "Machine-Learnable" features:
- `duration_num`: Extracted integers from strings (e.g., "90 min" → 90) for mathematical modeling.
- `cast_count`: Converted long actor lists into a numerical count of the production's scale.
- `primary_genre` & `primary_country`: Isolated the lead category/origin for cleaner grouping.

## 📊 Key Insights from EDA
- **The Pivot:** TV Shows have seen an exponential growth surge since 2015, challenging the historical dominance of Movies.
- **Maturity Profile:** The platform is heavily skewed toward **TV-MA** (Mature Audiences).
- **Survival Rate:** Univariate analysis shows a significant drop-off in TV Shows after **Season 1**, highlighting a high content churn.
- **Duration Stability:** Despite the "short attention span" myth, movie lengths have remained stable at an average of **99 minutes**.

## 🤖 Machine Learning (The Next Phase)
We are currently transitioning into the **Machine Learning** phase. 
- **Objective:** Build a Content-Based Filtering System.
- **Technique:** Natural Language Processing (NLP) using `CountVectorizer`.
- **Logic:** Building a "Metadata Soup" (Director + Cast + Genres + Description) and using **Cosine Similarity** to calculate the mathematical distance between titles.

---
**Author:** JANET CHEPKURUI

