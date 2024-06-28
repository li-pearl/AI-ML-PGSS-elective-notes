# Lecture 2 - 6/28/24

## Dimensionality Reduction

- Our data naturally resides in higher dimensions
- Reducing the dimensionality makes the problem more tractable
- And simultaneously provides us with insight

"Learning" is often finding an effective compressed representation.

> Follow triangle Dimensionality Reduction badge in the slides to follow this theme

### Why all these dimensions?

| Category     | Purchase Total ($) |
| ----------- | ----------- |
| Children's Clothing      | 800      |
| Pet Supplies  | 0 |
| Cameras | 450 |
| Containers | 350 |
| ... 2900 categories ... | ... |

*This is a 2900 dimensional vector*

We can use the clustering algorithm to find 80 clusters (with acceptable error)

People spending on "child's toys" and "children's clothing" must cluster with "child's books" and "cameras (Baby monitors, security cameras)." We also don't need to label clusters at all.

We can now represent any customer by their distance from these 80 clusters.

This accomplishes the following:
- Compresses our data
- Learned something about customers
    - Ex: Targeted ads

Customer Representation

| Cluster | Young Parents | College Athletes | Auto Enthusiast |etc. |
|-----| --- | --- | --- | --- |
|Distance | 0.02 | 2.3 | 1.4 | etc.

<blockquote>

### Supervised vs. Unsupervised Machine Learning

__Supervised:__ Human creates input labels

__Unsupervised:__ algorithm is free to interpret and process data on its own

__<span style="color: green">Clustering is unsupervised</span>__

</blockquote>

This compression of dimensions is considered *lossy compression* because there was data lost.

## Curse of Dimensionality

Recursive dimensionality

Our intuition can lead us astray as we increase the dimensionality of our problems - which we will certainly be doing - and to a great degree. There are several related aspects to this phenomenon, often referred to as the *Curse of Dimensionality*. 

- One root cause of this confusion is that our notion of Euclidian distance starts to fail in higher dimensions.

--- 

- __Distance between random points in space are almost all the same distance from each other in higher dimensions__

This can create problems for clustering algorithms because the computer can have trouble trying to group clusters based on distance

Other effects:
- Random vectores are almost all orthogonal (perpendicular to each other)
- The unit sphere thakes almost no volume in the unit square
- These cause all kinds of problems when generalizing algorithms in our 3D worlds

## Metrics
 The defition of distance (the metric) can vary based upon applications
 
 For chess problems, Manhattan distance (or taxicab metric) might be most useful

 You could choose between multiple different metrics for spell checking (one good for phonetic distance or edit distance), NLP (tokens), genomics (string sequences), text strings, etc.

 Some useful measures don't qualify as metrics (most likely because they fail the triangle inequality: *a + b > c*)

 ## Principal Component Analysis (PCA)

 Deep Learning techniques are much more powerful than this but it is the most popular tool to analyze data

 - A linear algebra algorithm
 - Start with a higher dimensional data set
 - PCA gives back a vector whose components reflect the strongest connections in the data
    - You could get back multiple vectors 
- It also gives back how much "fuzziness" there is
- Extracts the Principal Components


 - We are often inputting large and complex data-sets, and the visible end result is usually a 2D graph
 - Only one application of the more fundamental principle compoents
    - Example: Chromosome analysis

 Projecting the data down into less dimensions

 PCA has limitations
 It tells you what you should do in the simplest world, but the world isn't always simple

 It can sometimes fool you.

 