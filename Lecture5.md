# Lecture 5 - 7/10/24

```python
import tensorflow as tf

mindst = tf.keras.datasets.mnist
(train_images, train_labels), (test_images, test_labels) = mnist.load_data()

train_images = train_images.reshape(60000, 784)
test_images = test_images.reshape(10000, 784)

```

## Why Softmax?

The values from the matrix operations can have large and negative values. We want the solution vector to be conventional probabilities that sum to 1.0

Softmax function normalizes our outputs.

## Cross Entropy

- The Cross Entropy Loss function is a good way to define the error across all possibilities

- Better than squared error

- Defined as the -summation y_ log y, or if this really is a "0", y_=(1,0,0), and

- Somewhat penalizes a slightly wrong guess/"unconfident" right guess, and greatly penalizes a very wrong guess

- "undoes" the softmax

## Overfitting

- One solution, keep using higher order terms but to penalize theme

- Regularization hyperparameters

### Brute Force Doesn't Work

> Overfitting = memory

When there are enough parameters that the network is prone to memorizing instead of learning. Only gets worse as networks grow into billions of parameters

## CNNs

AlexNet

## Convolution


