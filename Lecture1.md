
# Lecture 1 - 6/26/24

> These notes are very incomplete and scattered

Hands-on registration: https://identity.access-ci.org/new-user

Email username to urbanic@psc.edu 


- Storage got cheap, keep all of it
    - Facebook
    - Deep Learning
    - IoT
    - Science
- 3 V’s of Big Data
    - Volume
    - Velocity
    - Variety
- SQL couldn’t keep up
    - Schemas set in stone:
    - Need to define before we can add data
    - Not a fit for agile development
    - Queries often require accessing multiple indexes and joining and sorting 
- Graph Database
    - Great for semantic web and graphs
    - Can be hard to visualize
    - Serialization can be difficult
    - Ex: Facebook, LinkedIn
- Queries
    - SPARQL
    - Cypher
- Frameworks for Data
    - Hadoop
        - Focuses on disk based data and a basic map-reduce scheme
    - Spark
        - Evolves Hadoop
        - Can accommodate multiple types of databases and achieve their performance gains by using parallel workers

## Intro to Machine Learning

### Clustering
- Most common operation for finding grouping in data 
- Has many applications
- Can be one part of a larger pipeline
- Presents challenges
    - Sometimes you don’t know how many clusters you have to start with
    - What exactly counts as a cluster
        - Example: From 1900 to 1956 humans were considered to have 48 chromosomes instead of 46, based upon the interpretation of clusters in a camera lucida image

#### Code Example

SparkContext available as sc, HiveContext available as sqlContext

```python
# V2.7.5

#Read into RDD
rdd1 = sc.textFile("5000_points.txt")

#Transform
rdd2 = rdd1.map(lambda x:x.split())
rdd3 = rdd2.map(lambda x: [int(x[0]), int(x[1])])

#Import Kmeans
from pyspark.mllib.clustering import KMeans
```

- Finds which areas are closest to each other
- Hard to tell what the exact answer is 
- The algorithm can't tell you how many clusters there are, but we can force the computer to assume there are a certain amount of clusters and compare the error between the center of the cluster. Where the error starts to become low, we can estimate the amount of clusters

#### Comparing Fit 

```python
for trials in range(10):
    print
    for clusters in range(12,18):
        model = KMeans.train(rdd3,clusters)
        print(clusters, model.computeCode(rdd3))

# Check Lecture Slides for the dataset
```

- There aren't not exactly deterministic results 

- Real-World Applications
    - LIGO gravitational wave detector confirms the collison of 2 neutron stars with gamma ray satellite and telescopes
    - Square Kilometer Array with generate over an Exabyte of data a day
    - Detection of an extremely strong magnetar radio signal