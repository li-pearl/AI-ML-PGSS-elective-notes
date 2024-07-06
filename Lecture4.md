# Lecture 4 - 7/5/24

## Inference
> Multiply, Add, do something non-linear

### __As a Matrix Operation__

#### Example:

$$
Sig(
\begin{bmatrix}
1.0 & -2.0 & 2.0\\
2.0 & 1.0 & -4.0\\
1.0 & -1.0 & 0.0
\end{bmatrix}
\begin{bmatrix}
0.5\\
0.9\\
-0.3
\end{bmatrix}
)
= Sig(
    \begin{bmatrix}
    -1.9 & 3.1 * -0.4
    \end{bmatrix}
)
=     
\begin{bmatrix}
0.13 & 0.96 * 0.4
\end{bmatrix}
$$

What does that mean:
$$
Sig(
\begin{bmatrix}
Hidden Layer Inputs
\end{bmatrix}
\begin{bmatrix}
Inputs
\end{bmatrix}
)
= Sig(
    \begin{bmatrix}
    -1.9 & 3.1 * -0.4
    \end{bmatrix}
)
=     
\begin{bmatrix}
Hidden Layer Outputs
\end{bmatrix}
$$

Can put this through a GPU (Vector matrix multiplication)

## Biases

Offseing our inputs by some constan. "Centering the activation fucntion"/translating the solution. Often one value per layer

## Linear + Nonlinear
1) Weapply linear operations (which look naturally like linear algebra matrix operations)
2) Pipe the final result through some kind of final nonliner activation function

> Combination of these allows us to do very general transformations

- The matrix multiple provides the *skew, rotation,* and *scale*
- The bias provides the *translation*
- The activation function provides the *warp*

## Width of Network

The width of any layer determines how many dimensions it can work in

- It takes at least 3 units wide to do this, regardless of depth
- Greater depth allows us to stack these operations
- The gains from depth are harder to characterize

> __Universal Approximation Theorem:__ A 1-hidden-layer feedforward network of this type can approximate any function, given enough width

Not really that useful because
1) Width could be enormous
2) Doesn't tell how to find the correct weights

## Training Neural Networks
How to find the weights?
- Minimize the error on our training data
- Select weights thhat generate the smallest average error on the outputs given labeled inputs

Output is a functon of the weights. 

The role of the gradient means that it becomes a rpoblem if it vanishes.
Issue for very deep networks

## Back-Propagation

The chain rule results in a lot of factors for any given weight adjustment in a useful network

### The Problem:

- The number of terms in the sum (# of paths) can grow exponentially with depth because the # of paths from 1 node to a distant node can grow exponentially.
- The same computation for the subfactors would be redone many times --> more cost

### The Solution:

__Back-propagation:__ Works as a table-filling algorithm that stores intermediate results and avoids repeating many common subexpressions

The details: 

https://colah.github.io/posts/2015-08-Backprop

https://www.youtube.com/watch?v=Ilg3gGewQ5U

Usually handled by TensorFlow or the package being used

## Solvers

Still leaves potentially many millions of simultaneous equations to solve

Solution space is non-convex

Gradient descent: The standard

Hyperparameters:
- Momentum: Most interesting recent methods incorporate this to help get over a local minimum
- Step size(learning rate):


We don't expect to find the actual global minimum

Instead:

We should find the error for all training data before updating the weights (an __epoch__).

__Stochastic approach__:
- More efficient
- Sampling a random subset of the data, updating the weights, and then repeating with another __mini-batch__

## Hands-On

On GPU Node
```
bridges2-login014% interact -gpu
v001%
```
Load the TensorFlow 2 Container:
```
v001% singularity shell --nv /ocean/containers/ngc/tensorflow/tensorflow_23.04-tf2-py3.sif
```
Start TensorFlow (Keras interface):
```
Singularity> python
Python 3.8.10 (default, Mar 13 2023, 10:26:41)
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow
>>> ...some congratulatory noise...
>>>
```

Tensorflow Docs: https://www.tensorflow.org/api_docs

### Handwriting Recognition

Trained on a large set of 28x28 greyscale samples

```python
import tensorflow as tf

mnist = tf.keras.datasets.mnist (train_images, train_labels), (test_images, test_labels) = mnist.load_data()

train_images = train_images.reshape(60000, 784)
test_images = test_images.reshape(10000, 784)

test_images = test_images.astype('float32')
train_images = train_images.astype('float32')

test_images /= 255
train_images /= 255
```