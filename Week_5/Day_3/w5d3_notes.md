# W5D3 notes

## This Week

## Today

Ensemble algorithms

- often have better prediction ability than linear logistic regression
- black box
- lower interpretability (sometimes a deal-breaker in business)
- a lot of fun and very mighty

Decision trees 🌳

## Lecture

### Topics

- Decision trees
  - Regression trees
  - Classification trees

- Random forests  
- Ensembles
  - Bagging
  - Boosting
  - Stacking

## Core

### Decision Trees

- widely used for classification and regression tasks
- a must-know concept

#### What is a Decision Tree?

- a non-parametric supervised learning method used for classification and regression
- approximate a curve with a set of if-then-else decision rules

To choose which feature to use as the root of the tree calculate minimum Gini impurity.

#### [Decision Tree Classification in Python](https://www.datacamp.com/community/tutorials/decision-tree-classification-python)

>The decision tree is a distribution-free or non-parametric method, which does not depend upon probability distribution assumptions.

##### Attribute Selection Measures/Splitting Rules

- Information Gain
    - Decrease entropy
    > Information gain computes the difference between entropy before split and average entropy after split of the dataset based on given attribute values.

    >Information gain is biased for the attribute with many outcomes. It means it prefers the attribute with a large number of distinct values.

    > The attribute A with the highest information gain, Gain(A), is chosen as the splitting attribute at node N().
- Gain Ratio
    > Gain ratio handles the issue of bias by normalizing the information gain using Split Info.

    >The attribute with the highest gain ratio is chosen as the splitting attribute
- Gini Index
    >The attribute with minimum Gini index is chosen as the splitting attribute.

### Random Forest

Feature importance
> Feature importance in random forests is the ratio of how many times the feature was used in all trees that were created vs. number of trees in the forest.

### Ensemble Learning

[Ensemble methods: bagging, boosting and stacking](https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205)  
Combine multiple models to improve model results

weak learners/base models have high bias or varience with sub-optimal performance on their own  
strong learner/ensemble models acheive better performance by combining multiple weak learners

Homogeneous ensembles uses one base learning algorithm  
Heterogeneous ensembles use different base learning algorithms
>One important point is that our choice of weak learners should be coherent with the way we aggregate these models. If we choose base models with low bias but high variance, it should be with an aggregating method that tends to reduce variance whereas if we choose base models with low variance but high bias, it should be with an aggregating method that tends to reduce bias.

Meta-algorithms for combining weak learners

- BAgging (Bootstrap aggregating)
  - homogeneous
  - parallel
  - main focus: reduce varience, more robust
- boosting
  - homogeneous
  - series
  - main focus: reduce bias
- stacking
  - heterogeneous
  - parallel
  - main focus: reduce bias

#### BAgging

- combine base models with a deterministic algorithm

Bootstrapping
>This statistical technique consists in generating samples of size B (called bootstrap samples) from an initial dataset of size N by randomly drawing with replacement B observations.

- almost representative
- almost independent
- i.e. approximatively independent and identically distributed (i.i.d.)

Train L almost independent weak learners for L ~iid bootstrap samples and aggregate the outputs to reduce variance of output.

Aggregation methods:

- Regression, simple average
- classification
  - majority vote/hard voting
  - highest average probability/soft voting

#### Random forests

Shallow trees, less variance, higher bias, better for series/sequential learning to reduce bias

Deep trees, higher variance, low bias, better for parralel learning with bagging to reduce varience

Bagging

- bootstrap sample over observations (rows) and features (columns), reducing correlation between trees' outputs
- more robust to missing data

#### Boosting

> each model in the sequence is fitted giving more importance to observations in the dataset that were badly handled by the previous models in the sequence. Intuitively, each new model focus its efforts on the most difficult observations to fit up to now, so that we obtain, at the end of the process, a strong learner with lower bias (even if we can notice that boosting can also have the effect of reducing variance)

- If using trees, make them shallow for low varience and high bias
- combine base models with a deterministic algorithm

algorithms

- adaboost
  - updates the weights attached to each of the training dataset observations
- gradient boost
  - updates the value of these observation

Adaptive boosting (adaboost)

- weighted sum of L weak learners

>- fit the best possible weak model with the current observations weights
>- compute the value of the update coefficient that is some kind of scalar evaluation metric of the weak learner that indicates how much this weak learner should be taken into account into the ensemble model
>- update the strong learner by adding the new weak learner multiplied by its update coefficient
>- compute new observations weights that expresse which observations we would like to focus on at the next iteration (weights of observations wrongly predicted by the aggregated model increase and weights of the correctly predicted observations decrease)

Gradient boosting

- weighted sum of L weak learners
- cast as a gradient descent problem

>- fit the best possible weak learner to pseudo-residuals (approximate the opposite of the gradient with respect to the current strong learner)
>- compute the value of the optimal step size that defines by how much we update the ensemble model in the direction of the new weak learner
>- update the ensemble model by adding the new weak learner multiplied by the step size (make a step of gradient descent)
>- compute new pseudo-residuals that indicate, for each observation, in which direction we would like to update next the ensemble model predictions

>gradient boosting can be considered as a generalization of adaboost to arbitrary differentiable loss functions.

#### Stacking

- combine base models using a meta-model

> So, assume that we want to fit a stacking ensemble composed of L weak learners. Then we have to follow the steps thereafter:

>- split the training data in two folds
>- choose L weak learners and fit them to data of the first fold
>- for each of the L weak learners, make predictions for observations in the second fold
>- fit the meta-model on the second fold, using predictions made by the weak learners as inputs

- half the data trains the base models
- half the data trains the meta-model
- use k-fold cross-training to use all data

Multi-level stacking

- Level 1 L base models
- Level 2 M meta models
- Level 3 One meta model

### XGBoost

[Complete Guide to Parameter Tuning in XGBoost with codes in Python](https://www.analyticsvidhya.com/blog/2016/03/complete-guide-parameter-tuning-xgboost-with-codes-python/)
