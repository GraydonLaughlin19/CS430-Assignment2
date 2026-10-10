# CS 430 Assignment 2: SLCM Regression Analysis

**Course:** CS 430 Machine Learning
**Student:** Graydon Laughlin

## Overview

This repository contains my work for Assignment 2. The goal is to predict `past_due_rent` for households in the SLCM rent arrears dataset and to compare four regression models.

## Files

- `Assignment_2Finished.ipynb`: the notebook with all code, outputs, and written answers (Questions 1-17).
- `SLCM_rent_arrears_student_clean.csv`: the dataset (1,754 rows, 14 columns).
- `README.md`: this file.

## Models compared

All models use the same preprocessing pipeline (median imputation and scaling for numeric columns, most-frequent imputation and one-hot encoding for categorical columns), an 80/20 train/test split, and `random_state=42`.

1. Linear Regression
2. Polynomial Regression (degree 2, `include_bias=False`, numeric columns only)
3. Ridge Regression (alphas tested: 1, 10, 100, 1000)
4. Lasso Regression (alphas tested: 1, 10, 100)

## Results (test set)

| Model | RMSE | R² |
|---|---|---|
| Linear | 1861.21 | 0.155 |
| Polynomial | 1875.04 | 0.142 |
| Ridge (alpha=100) | 1837.41 | 0.176 |
| Lasso (alpha=10) | 1826.44 | 0.186 |

Lasso had the lowest RMSE and highest R². Even so, all four models explain only a small share of the variation in past-due rent, so predictions should be treated as rough estimates.

## How to run

1. Place `SLCM_rent_arrears_student_clean.csv` in the same folder as the notebook.
2. Open the notebook in Jupyter or Google Colab.
3. Choose Restart & Run All. It should run start to finish without errors.

Requires Python 3 with `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn`.

## Notes

- `record_id` is excluded from the features because it is only an identifier.
- Results describe associations in this dataset, not causes.
- AI assistance was permitted for this assignment by Dr. Sarkar.
