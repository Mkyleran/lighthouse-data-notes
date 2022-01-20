# W5D5–W6D5 notes

## Today

Mid-Term Project

## Lecture

### Topics

- About the midterm project
- The skeleton of the project
- How to plan the project
- How to divide up tasks
- How to collaborate with Git (Simple Git Workflow)
- How will the project be evaluated
  - modeling results
  - presentation
  - code review

## Mid-term Project

- only train on the features available in testing
- Query other APIs (e.g. weather)
- Save DB queries to csv

Lifecycle

1. Original Data
2. Preprocessing / Clean Data
3. Exploritory Data Analysis EDA
4. Feature Selection
5. Model Selection
    - Cross validation on training set
6. Hyperparameter Tuning
7. Prediction & Deployment

Get a minimum viable product (MVP) early

Causes of arrival delay

- weather
- mechanical
- congestion
- late arrivals
- late flight crew
- late passengers

### Collaboration

Motivation
Task
Modeling
Results
Conclusions

Code quality

- modularization different files for different steps of the ML pipeline

Persist a model in a pickle file.

### Notes

To get a representative sample of a large data set, use the Central Limit Theorem  
Stop condition

- when the change in the mean of a feature drops below a threshold. i.e. slope goes to 0.
- when the sample mean reaches a tolerance of the population mean
