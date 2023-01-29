# W8D1 notes

## This Week

## Today

Deep Learning

## Lecture

### Topics

- Introduction to Deep Learning
  - Neural Networks
  - Case Studies
  - ML vs. DL
- Deep Learning Libraries
- How do Neural Networks learn?
  - Backpropagation

## Core

### [Pros and Cons of Deep Learning](https://data.compass.lighthouselabs.ca/days/w08d1/activities/679)

Article: [Why are deep learning models so popular?](https://dev.solita.fi/2018/02/12/deep-learning-popularity.html) Feb 2018

- DL is good for unstructured data
- In a NN, the number of parameters/weights is strictly determined beforehand like a parametric model, but there are a large number of weights some of which will zero out, blocking certain pathways more like a nonparametric model.
- NN are non-linear
- The basic NN can be adapted to work in different use cases. CNN for images, RNN for time-series or nlp
- NN has low explainability (black box)
- NN requires large amounts of data

### [Neural Networks](https://data.compass.lighthouselabs.ca/days/w08d1/activities/680)

Video: [But what is a neural network? | Chapter 1, Deep learning](https://www.youtube.com/watch?v=aircAruvnKk)

- vanilla NN: multi-layer perceptron
- output layer gives the probability of each output neuron
- feed-forward
- each layer uses an activation function (sigmoid, ReLu) to keep each layer output between 0 and 1

### [How Neural Network Learns](https://data.compass.lighthouselabs.ca/days/w08d1/activities/683)

Video: [Gradient descent, how neural networks learn | Chapter 2, Deep learning](https://www.youtube.com/watch?v=IHZwWFHWa-w)

- cost function: average of the sum of squared error over all training data
- gradient decent determines how to change the input weights to maximally decrease the output (cost/error)
- cost is the average error over all training data
- backpropagation is the algorithm for computing the gradient which is is how the NN learns
- learning is minimizing the cost function
- Resource: textbook [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com)

### [Backpropagation](https://data.compass.lighthouselabs.ca/days/w08d1/activities/684)

The process of weight optimization in NN

Video: [What is backpropagation really doing? | Chapter 3, Deep learning](https://www.youtube.com/watch?v=Ilg3gGewQ5U)

- backpropagation is the algorithm for computing the gradient which is is how the NN learns
- Calculating the changes for every training example is very expensive. Therefore, shuffle the training data, and compute the changes for mini-batches. It's a decent approximation and much quicker. Stocastic gradient decent.
- Crowdflower is a way to get data annotated by people

### [Calculus in Backpropagation](https://data.compass.lighthouselabs.ca/days/w08d1/activities/690)

Video: [Backpropagation calculus | Chapter 4, Deep learning](https://www.youtube.com/watch?v=tIeHLnjs5U8)

- calculus chain rule
- That made a lot more sense than the earlier videos.