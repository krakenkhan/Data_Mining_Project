# Data Mining Final Project

This repository contains the final project for a Data Mining course. The primary analysis is in the Jupyter notebook `Data_Mining_Final_Project.ipynb`

## Overview

The project explores the "Computer Hardware" dataset from the UCI Machine Learning Repository and analyzes factors that relate to relative CPU performance. The analysis covers data loading, basic inspection, exploratory data analysis, and notes on the target distribution and modeling considerations.

## Dataset

- Name: Computer Hardware (UCI)
- UCI page: https://archive.ics.uci.edu/dataset/29/computer+hardware
- Data URL (CSV): https://archive.ics.uci.edu/static/public/29/data.csv
- Description: Relative CPU performance data described using cycle time, memory sizes, cache, channel counts, and published/estimated relative performance metrics.
- Instances: 209
- Features (columns used in the notebook):
  - VendorName (categorical)
  - ModelName (categorical)
  - MYCT: machine cycle time in nanoseconds (integer)
  - MMIN: minimum main memory in kilobytes (integer)
  - MMAX: maximum main memory in kilobytes (integer)
  - CACH: cache memory in kilobytes (integer)
  - CHMIN: minimum channels in units (integer)
  - CHMAX: maximum channels in units (integer)
  - PRP: published relative performance (integer)
  - ERP: estimated relative performance (integer)

## Notebook

- File: `Data_Mining_Final_Project.ipynb`
- The notebook:
  - Fetches the dataset using the `ucimlrepo` helper.
  - Inspects metadata, variables, dtypes and missing values.
  - Creates a combined DataFrame for features + performance columns.
  - Visualizes PRP distribution and numeric feature histograms.
  - Shows top vendors by number of CPU models.
  - Notes that the PRP distribution is highly right-skewed (a few very high-performing chips).

## Key Findings / Notes

- PRP (published relative performance) is highly right-skewed and contains some extreme high values — consider a log-transform or robust methods if modeling PRP directly.
- No missing values are present in this dataset.
- Vendor and model are categorical; many models are unique, so model name is likely not useful as a direct predictive feature without feature engineering.
- Numeric features (MYCT, MMIN, MMAX, CACH, CHMIN, CHMAX) show varied distributions; consider standardization/normalization for modeling.


## License & Credits

- Dataset: UCI Machine Learning Repository (Jacob Feldmesser, 1987).

## Author

- Author: Munish Khan
- Notes: Project submitted as part of a Data Mining class.
