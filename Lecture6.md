# Lecture 6

## Emergent Capability

An emergent ability is an ability that is not present in small models but develops as the model is scaled. These might be unanticipated

## Data Augmentation

Supervised learning often requires human-labeled data. 
Data augmentation = Process of generating more training data from our existing pool
- Extremely common technique, especially for classification problems

- tf.image

Some techniques of data augmentation:
- Scale Invariance
- Rotation Invariance
- Noise Tolerance
- Translation Invariance

## One-Shot Learning

N-Shot learning does exist. It is harder, requires more specialized techniques, and is straying into the area of unsupervised learning.

Datasets: kaggle.com

------------------------------------

## Building Blocks

We have used fully connected and convolutional layers. There are many more others

- FC
- CNN
- ResNet Feed forward
- RNN Feedback but has vanishing gradients
- LSTM
- Attention based transformer

## Residual Neural Nets

Disappearing gradients can be an issue.

Method is to use some feedforward.

- Helps preserve reasonable gradients for very deep networks
- Very effective at imagery
- Used by AlphaGo Zero (40 residual CNN layers) in place of previous complex dual network
- 100s of layers common, pushing 100

## Recurrent Networks (RNNs)

Feedback

Currently at the center of many of the most effective techniques in deep learning

## LTSMs

Incorporate a memory into networks.

LSTM: A search space odessy

### Bi-directional LSTMs

Read the input from both directions to get more context

## Transformers

Natural Language Processing

Process sequential data, but with the ability to learn the relative importance of different, perhaps distant, tokens. In other words, pay more attention to some relationships than others.

While these designs have proven surprisingly powerful in NLP (emergent capability), they have yet to find a centrla use to scientific problems.

> Idea: Can this be used in genome analysis?

## Autoencoder

Encoder to compress to a lower dimensional space
Decoder to decompress

### Deepfake Network

Latent features = a "police sketch artist" description

swapping in input for another decoder

Image generation

## Discriminative vs. Generative

Discriminative models classify things, and need only know which side of the hyper-plane the instance lies on.
- Only need to capture the conditional probability of digit Y given image X: P(Y|X)

Generative models need to understand the distribution to generate new instances
- Must understand the joint probability P(X,Y)

## Generative Networks

### Architectures

With the layers we have discussed, we can build countless different networks (and use Tensorflow to defin them). The current "building block" is actually a functional network.

- YOLO (You Only Look Once)
- Generative Adversarial Network
- AlexNet
- Mask R-CNN
- GoogLeNet/Inception



