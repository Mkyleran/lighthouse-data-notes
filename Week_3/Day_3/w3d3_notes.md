# WD notes

## Today

Introduction to ML Process  
Data Prep  
Feature Engineering

## Lecture

## Core

7 Steps of ML

1. Gathering data
2. Preparing that data
    1. Data Exploration:
        - Explore data
        - Explore the target variable (if we have one)
    2. Find relationships between target and other variables
    3. Data cleaning
        - Missing values
        - Outlier detection
3. Choosing a model
4. Training
5. Evaluation
6. Hyperparameter tuning
7. Prediction

### [Best practices for Data Prep](https://www.import.io/post/10-best-practices-data-preparation/)

1. Data Governance
    >a necessary “wrapper” that defines the business objectives, business glossary definitions, data quality, data auditing, and data lineage standards that data preparation efforts must meet
2. Start With Good “Raw Material”
3. Extract Data to a Good “Work Bench”
4. Spend the Right Amount of Time on Data Profiling
5. For big data sets start with a small sample
6. Zero in on Data Types
7. Your Data Ought to be in Pictures
8. Don’t Forget the Sanity Check
    - Does the data make sense
9. Iteratively Cleanse and Filter
10. Apply the data prep steps to the full data set

### Data Exploration

- Univariate Analysis
  - Categorical
    - nominal
    - ordinal
  - Numerical
    - interval
    - ratio
- Bivariate Analysis
  - Numerical & Numerical
    - Scatter plot
    - Linear correlation
  - Categorical & Categorical
    - Stacked column
    - Combo-chart
    - Chi-squared test
  - Numerical & Categorical
    - Line chart with error bars
    - Combo-chart
    - Z-test
    - T-test
    - ANOVA
