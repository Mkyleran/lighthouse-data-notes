# W7D1 notes

## This Week

Pipelines and Deployment

## Today

Model Persistance and Pipelines

## Lecture

### Topics

- Model Persistence - how to store training models
- Advanced hyperparameter tuning
  - How to tune more than model parameters

## Core

- Pickle
- Joblib
- Tuning Parameters
- Pipelines

### Object Serialization

Python and library major versions and likely minor versions need to be the same in the loading environment as the dumping environment

Joblib: more efficient than pickle on objects that carry large numpy arrays internally, which is often the case for fitted Sklearn estimators

### Advanced Tuning of Parameters
