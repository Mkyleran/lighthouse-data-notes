# WD2 notes

## Today

Deep Learning II

## Lecture

### Topics

- Different DL Architectures
  - CNN
  - RNN
  - LSTM
- Evolution of DL Architectures
- Best practices when designing a network
- Image Recognition

## Core

### [From Neural Nets to Deep Learning](https://data.compass.lighthouselabs.ca/days/w08d2/activities/693)

Article: [Artificial Neural Networks and Deep Learning](https://becominghuman.ai/artificial-neural-networks-and-deep-learning-a3c9136f2137) Jan 30, 2018

- More complex Neural Networks are Deep Neural Networks (more than 3 layers, i.e. more than one hidden layer. More neurons too)
- Training Deep Neural Networks is called Deep Learning

### [Different DL Architectures](https://data.compass.lighthouselabs.ca/days/w08d2/activities/694)

Article: [Deep Learning: Common Architectures](https://srnghn.medium.com/deep-learning-common-architectures-6071d47cb383) Aug 14, 2018

Architectures

- Multi-layer Perceptrons (MLP)
  - at least 3 layers
  - each node in a layer connects to every node in the next layer
  - useful for structured data
  - Good for baseline model
- Convolutional Neural Networks
  - often used for images
  - accounts for spacial relation (i.e. a pixel has 8 neighbors)
  - pooling and flattening
  - the flattened CNN is passed to a final MLP
- Recurrent Neural Networks
  - memory
  - time series, historic trends to predict future
  - NLP, linguistic context to predict next word
- Hybrid
  - models can be combined. Think of a CNN that extracts text from an image and then determines the sentiment of that text

### [CNN](https://data.compass.lighthouselabs.ca/days/w08d2/activities/695)

Video: [How Convolutional Neural Networks work](https://www.youtube.com/watch?v=FmpDIaiMIeA) Aug 18, 2016

>It's not magic, it's simply linear algebra

Good for any data where proximity/order matters. Local spacial patterns.

A filter is a small segment of a larger image

Filtering:

1. Line up the feature and the image patch
2. Multiply each image pixel by the corresponding feature pixel
3. Add them up
4. Divide by the total number of pixels in the feature

Convolution: repeatedly testing the filter over the entire image. Each pixel of a convolved/filtered image is a measure of how well the filter/feature matched the original image.

A convolution layer is the stack of filtered images. One for each filter/feature being tested.

Pooling: Shrinking the filtered images

1. Pick a window size (usually 2 or 3)
2. Pick a stride (usually 2)
3. Walk  your window across your filtered images
4. From each window, take the maximum value.

Normalization: keep the math from blowing up

- Rectified Linear Units (ReLU). Set all negative values to 0

Fully connected layer: Unravel all final filtered images into a single layer.

Backpropagation lets the CNN learn the filter features. Error drives gradient decent.

Hyperparameters

- Convolution
  - Number of features
  - Size of features
- Pooling
  - Window size
  - Window stride
- Fully Connected
  - Number of neurons
- Architecture
  - How many of each type of layer
  - In what order?

Resources:

- Deep Learning Demystified
- Notes from Stanford CS 231 course with Justin Johnson and Andrej Karpathy
- Christopher Olah
- Caffe
- CNTK
- Deeplearning4j
- TensorFlow
- Theano
- Torch

Ways to optimize CNN
[How to Develop a CNN From Scratch for CIFAR-10 Photo Classification](https://machinelearningmastery.com/how-to-develop-a-cnn-from-scratch-for-cifar-10-photo-classification/)

## RNN



## Long Short-Term Memory Network

