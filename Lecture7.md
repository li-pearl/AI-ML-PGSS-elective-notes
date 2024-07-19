# Lecture 7 - 7/19/24

> Last one best one!

## Some Taxonomies

- Clasiffication
- Localization
- Detection
- Segmentation

These tasks would call for different network designs

These classifications don't have super strict defined boundaries.

They are just useful ways to keep track of the explosion of options in this space.

## Tasks

- Classification
- Regression: Return a value. _Stock price_
- Transcription: Convert between representations, _OCR, speech recognition_
- Synthesis: Create a new input examples. _Speech synthesizer._
- Translation: _Google Translate_
- Segmentation: Return a relabeled input vector, _tumor detection_
- Denoising: Return uncorrupted example, _ray tracing_

## Learning Approaches

- Supervised Learning
  - How you learned colors
  - Used for: image recognition, tumor identification, segmentation
  - Requires labeled data. Lots of it. Augmenting helps
  - Essence: Learning to map one vector to another, given enough examples of the ampping

- Unsupervised Learning
  - (Maybe) how you learned to see
  - What we did earlier with clustering and our recommender, and Deepfake
  - Find patterns in data, compress data into model, find reducible representation of data
  - Used for: Learning from unlabeled data
  - Might be a great way to bootstrap Supervised Learning (train an autoencoder and build from those weights)

- Reinforcement Learning:
  - How you learned to walk
  - Requires goals (maybe long term, i.e. arbitrary delays between action and reward)
  - Used for: Go (AlphaGo Zero), robot motion, video games
  - Don't just read data, but interact with it

All of these have been done with ane without deep learning. DL has moved to the forefront of all of these

## AI Based Simulation

- Model-Free Prediction of Large Spatiotemporally Chaotic Systems from Data: A Reservoir Computing Approach (Pathak et al 2018)

- Pushing the Limit of Molecular Dynamics with Ab Initio Accuracy to 100 Million Atoms with Machine Learning (Jia et al 2020)

> ### A Problem to Try

> Fluid dyanmics over a car

> NVIDIA's GPU Bootcamp materials conatin this example. Learn a mapping from boundary conditions to steady state fluid flow. 

### Three Body Problem

## Has Deep Learning left any room for other approaches

### "Theoretician's Nightmare" and Other Perspectives

- Paraphrasing Yann LeCun, godfather of Deep Learning

- Oddly empirical branch of CS

- Many of these techniques were developed through experimentation, and many of them are not amenable to classical analysis. A theoretician would suggest that non-convex loss functions are at the heart of the matter, and that situation isn't getting better, as many of the latest techniques have made this much worse.

- Many techniques we use today have very recent provenance.

### Survey of the Field

#### XGBoost and Trees

XGBoost is the latest, and most popular, evolution of the Decision Tree approach

Gradient Boosted Trees (error decreases as iterations increases)

One of the few algorithms that is non-linear

## Hardware

GPUs, NVIDIA

Reading:

Deep Learning for AI Turing Lecture
  



