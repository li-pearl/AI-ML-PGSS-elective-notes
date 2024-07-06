# Lecture 3 - 7/3/24

## PCA 
PCA is limited because it is linear

### Why So Many Alternatives?

Home Data:

| Latitude | 4833438 north |
| --- | ---- | 
|Longitude | 630084 east|
|Last Sale Price|$480,000|
|Last Sale Year|1998|
|...|...|

There may be some opportunities to reduce the dimension of the vector by clustering on geographical coordinate.

Or we could cluster on the size of the house (width and depth)

PCA Fails here. 
House price for width and depth

It can only consider it separately, when in reality, price is more dependent on square footage (width x depth)

### Why the fascination with linear techniques?

__The Streetlight Effect__

"We want to use the tools that we know how to work even if it's not the most powerful for it"

 - This is a very real and powerful force throughout the sciences
- It is not because practitioners are dumb.
- But, it is also very often niether explained nor justified, leading to great confusion.



## Central Hypothesis of Modern DL

<blockquote>

### <ins>Example: </ins>
#### Multi-dimensional data (Images):

MNIST 28x28 greyscale images = 784 dimensions
</blockquote>

- Data lives on a lower dimensional manifold
- Maybe very contiguous
- Maybe a small set of disconnected

### Testing These Ideas With Sci-kit Learn

## Defining our error
Defining the error/loss/cost is often the core of defining the objective solution. It can be obvous, or very suble, or have multiple acceptanle methods

Issues that arise when defining error:
- Clustering:
- Image Recognition:
- Regression:
- Rare events:


Some of the capabilities, especially the generative ones, defy simple quantification

Ex: GPT-4 can recognize humor, write poetry, generate art

However, it's hard to quantify those areas and give it number-based feedback for it to get better

## Overfitting

> How do you connect the dots?

Driving the error to zero is not really what we want. The error can be zero, but you won't learn anything from it. 

> Example: Instead of fitting 5 data points to a quadratic, fitting it to a 4 point curve to make the error 0. Although the error is 0, the quadratic is probably the actual relationship but that won't be what we observe if we overfit the data (instead we will observe a less-likely 4 point curve that probably won't hold with the addition of more data points proving the quadratic relationship)

## Unprecedented Disruption

In the history of science, there has never been one that has happened this quick.

__10 years ago:__

People wouldn't have believed you to be able to do the following in the near future:

- "Neural nets will enable real time ray tracing"
- "Neural nets will do protein folding"

__5 years ago:__

Same thing with 5 years ago. People wouldn't believe you to be able to do this in the near future:
- "Neurel nets will do CFD"

__Today:__

Neurel net enabled algorithms are the ebst way to do protein folding.

This revolution caught everyone, including those who built it, off guard

__Tomorrow:__

"Neural nets will steal our jobs."

### Why Now?

The ideas have been around for decades. Two components came together in the past 15 years to enable astounding progress:

- Widespread parallel computing (GPUs)
- Big data training sets
    - Models learn by repetition and example

## Two Perspectives

There are 2 common ways to view the fundaments of Deep Learning

- Biology: Inspired by biological models
- Math: An evolution of classic ML techniques (the perceptron)

### Math: As a Highly Dimensional Non-linear Classifier

Perceptron:
- No Hidden layer
- Linear

Network:
- Hidden Layers
- Nonlinear

## Basic NN Architecture

100+ layers have become common
Deep NN vs. "Non-deep" feedforward neural network

Input layer values -> 
Weights for nuerons in hidden layer -> 
Weights for nuerons in output layer

### Activation Function

The __Sigmoid__ function produces a value between 0 and 1, so it is intuitieve when a probablity is desired, wand was almost standard for many years.

The __Rectified Linear__ activation function is zero when the input is negative and is equal to the input when the input is positive. Rectified Linear activation functions are currently the most popular activation function as they are more efficient than the sigmoid or hyperbolic tangent.

- Sparse activation: In a randomly initialized network, only 50% of hidden units are active
- Better gradient propagation: Fewer vanishing gradient problems compared to sigmoidal activation functions that saturate in both directions
- Efficient computation: Only comparison, maybe addition and multiplication for variants
- There are __Leaky__ and __Noisy__ varients

