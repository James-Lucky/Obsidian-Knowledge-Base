# UNIT I — Introduction to Deep Learning

This unit is mostly theory + basic mathematical understanding.  
In exams, teachers usually ask:

- definitions
- comparisons
- short notes
- explain algorithms
- derivations of gradient descent
- difference between ML and DL
- numerical on loss function or gradient descent

This is a **high-scoring unit** if prepared properly.

---

# 1. Introduction to Deep Learning

## What is Deep Learning?

Deep Learning is a subset of Machine Learning that uses **Artificial Neural Networks (ANNs)** with many layers to learn patterns from data.

It is inspired by the human brain.

Instead of manually extracting features, deep learning automatically learns features from raw data.

---

## Simple Definition

> Deep Learning is a machine learning technique where multi-layer neural networks learn complex patterns from large amounts of data.

---

## Real-Life Examples

|Application|Use|
|---|---|
|Face Recognition|Unlock phone|
|ChatGPT|Natural language understanding|
|Self-driving cars|Object detection|
|YouTube Recommendations|Personalized suggestions|
|Medical Imaging|Tumor detection|

---

# Why "Deep"?

Because neural networks contain multiple hidden layers.

Example:

Input Layer → Hidden Layer 1 → Hidden Layer 2 → Hidden Layer 3 → Output Layer

More hidden layers = “deep”.

---

# Traditional Programming vs Deep Learning

## Traditional Programming

Input + Rules → Output

Example:

- You manually write rules to identify spam email.

---

## Deep Learning

Input + Output examples → Model learns Rules

Example:

- Give thousands of spam emails.
- System automatically learns patterns.

---

# Advantages of Deep Learning

1. Automatic feature extraction
2. High accuracy
3. Works well with unstructured data
4. Learns complex patterns
5. Improves with more data

---

# Disadvantages

1. Requires huge data
2. Needs high computational power
3. Training takes time
4. Hard to interpret (“Black Box”)

---

# Architecture of Deep Learning

Basic Neural Network:

```
Input Layer → Hidden Layers → Output Layer
```

Each neuron:

- receives input
- performs weighted sum
- applies activation function
- passes output

---

# Important Exam Question

### Q. What is Deep Learning? Explain its advantages and applications.

---

# 2. Bayesian Learning

Bayesian Learning is based on **Bayes Theorem**.

It is a probabilistic approach used in machine learning.

---

# Bayes Theorem

P(A∣B)=P(B∣A)P(A)P(B)P(A|B)=\frac{P(B|A)P(A)}{P(B)}P(A∣B)=P(B)P(B∣A)P(A)​

P(A)P(A)P(A)

P(B∣A)P(B\mid A)P(B∣A)

P(B∣¬A)P(B\mid \neg A)P(B∣¬A)

P(A∣B)=P(B∣A)P(A)P(B)≈0.68,  P(B)≈0.25P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}\approx 0.68,\; P(B)\approx 0.25P(A∣B)=P(B)P(B∣A)P(A)​≈0.68,P(B)≈0.25

P(B)=0.25P(B|A)P(A)=0.17P(A|B)~0.68Posterior = useful evidence / total evidence

Where:

| Term | Meaning           |
| ---- | ----------------- |
| P(A  | B)                |
| P(B  | A)                |
| P(A) | Prior Probability |
| P(B) | Evidence          |

---

# Simple Meaning

Bayesian learning updates probability as more evidence becomes available.

---

# Example — Spam Email Detection

Suppose:

- 70% spam emails contain “FREE”
- You receive email containing “FREE”

Bayesian learning calculates probability that email is spam.

---

# Applications

1. Spam filtering
2. Medical diagnosis
3. Recommendation systems
4. Risk analysis

---

# Advantages

1. Works with uncertainty
2. Probabilistic predictions
3. Handles missing data

---

# Disadvantages

1. Computationally expensive
2. Assumes independence in Naive Bayes

---

# 3. Overview of Shallow Machine Learning

Shallow Learning means models with:

- few layers
- limited complexity

Usually:

- no hidden layer
- or single hidden layer

---

# Examples

|Algorithm|Type|
|---|---|
|Linear Regression|Shallow|
|Logistic Regression|Shallow|
|Decision Trees|Shallow|
|SVM|Shallow|

---

# Characteristics

1. Manual feature extraction required
2. Works on small datasets
3. Faster training
4. Less computational power

---

# Example

Suppose detecting cats in images.

In shallow ML:

- human manually extracts features like ears, tail, shape.

In deep learning:

- system automatically learns features.
---

# 4. Difference Between Deep Learning and Shallow Learning

This is VERY IMPORTANT for exams.

|Feature|Shallow Learning|Deep Learning|
|---|---|---|
|Layers|Few|Many|
|Feature Extraction|Manual|Automatic|
|Data Requirement|Small|Large|
|Hardware Need|Low|High|
|Accuracy|Moderate|High|
|Training Time|Fast|Slow|
|Complex Data Handling|Limited|Excellent|
|Examples|SVM, Regression|CNN, RNN|

---

# Short Exam Answer

> Shallow learning uses fewer layers and manual feature extraction, while deep learning uses multiple layers and automatic feature learning.

---

# 5. Linear Classifiers

A Linear Classifier separates data using a straight line (2D) or hyperplane (higher dimensions).

---

# Formula

y=wTx+by=w^Tx+by=wTx+b

Where:

- w = weights
- x = input
- b = bias

---

# Working

If output > threshold:

- Class A

Else:

- Class B

---

# Examples

1. Logistic Regression
2. Perceptron
3. Support Vector Machine (Linear SVM)

---

# Real-Life Example

Email classification:

- Spam or Not Spam

---

# Advantages

1. Simple
2. Fast
3. Easy to train

---

# Disadvantages

1. Cannot solve nonlinear problems
2. Limited complexity

---

# 6. Loss Function

Loss Function measures how wrong the model prediction is.

Lower loss = better model.

---

# Purpose

Used during training to improve model.

---

# Common Loss Functions

|Loss Function|Used For|
|---|---|
|Mean Squared Error (MSE)|Regression|
|Cross Entropy Loss|Classification|
|Hinge Loss|SVM|

---

# Mean Squared Error

MSE=1n∑i=1n(yi−y^i)2MSE=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2MSE=n1​∑i=1n​(yi​−y^​i​)2

Where:

- yi = actual value
- ŷi = predicted value

---

# Example

Actual = 10  
Predicted = 8

Loss:

```
(10 - 8)^2 = 4
```

---

# Why Squared?

To:

1. avoid negative values
2. penalize larger errors more

---

# 7. Optimization Techniques

Optimization means:

> adjusting model parameters to reduce loss.

Goal:

- minimize loss function
- improve prediction accuracy

---

# Most Important Optimization Method

# Gradient Descent

Very important for exam.

---

# Idea of Gradient Descent

Imagine standing on a mountain and trying to reach lowest point.

Gradient Descent:

- checks slope
- moves downward step-by-step

until minimum loss is reached.

---

# Formula

θ=θ−η∂J(θ)∂θ\theta=\theta-\eta\frac{\partial J(\theta)}{\partial \theta}θ=θ−η∂θ∂J(θ)​

Where:

- θ = parameter
- η = learning rate
- J(θ) = loss function

---

# Steps of Gradient Descent

1. Initialize weights
2. Compute prediction
3. Calculate loss
4. Compute gradient
5. Update weights
6. Repeat until minimum loss

---

# Learning Rate

Controls step size.

|Learning Rate|Result|
|---|---|
|Too Small|Slow training|
|Too Large|Overshooting|

---

# Types of Gradient Descent

|Type|Description|
|---|---|
|Batch Gradient Descent|Uses full dataset|
|Stochastic Gradient Descent|Uses one sample|
|Mini-batch Gradient Descent|Uses small batches|

---

# Batch Optimization

Batch optimization means:

- entire dataset used for one update.

---

# Advantages

1. Stable convergence
2. Accurate gradient

---

# Disadvantages

1. Slow for large datasets
2. High memory usage

---

# Example

Suppose dataset has 10,000 samples.

Batch Gradient Descent:

- processes all 10,000 before updating weights.

---

# Quick Revision Notes

## Deep Learning

- Multi-layer neural networks
- Automatic feature extraction

## Bayesian Learning

- Based on probability
- Uses Bayes theorem

## Shallow Learning

- Few layers
- Manual features

## Linear Classifier

- Separates data linearly

## Loss Function

- Measures prediction error

## Gradient Descent

- Minimizes loss iteratively

## Batch Optimization

- Uses complete dataset for update

# UNIT III — Training Deep Neural Networks

This unit is extremely important because it covers:

- training problems
- activation functions
- hyperparameter tuning
- RNN/LSTM/GRU architectures

Most teachers ask:

- compare RNN, LSTM, GRU
- explain vanishing gradient
- explain activation functions
- hyperparameter vs parameter
- why LSTM was introduced

This unit is concept-heavy. If you memorize definitions only, you’ll fail conceptual questions.

---

# 1. Training Deep Neural Networks

Training means:

- adjusting weights and biases
- minimizing loss
- improving predictions

---

# Basic Training Process

1. Input data
2. Forward propagation
3. Prediction
4. Loss calculation
5. Backpropagation
6. Weight update
7. Repeat

---

# Goal

Minimize error and maximize accuracy.

---

# Example

Suppose:

- image classifier predicts dog instead of cat

Training updates weights so next prediction improves.

---

# 2. Difficulty of Training Deep Neural Networks

VERY IMPORTANT THEORY TOPIC.

Deep networks are difficult to train because:

- many layers
- millions of parameters
- complex optimization

---

# Main Difficulties

---

# (1) Vanishing Gradient Problem

Most important problem.

During backpropagation:

- gradients become extremely small
- early layers stop learning

---

# Why Happens?

Because repeated multiplication of small derivatives causes values to approach zero.

Example:

```
0.1 × 0.1 × 0.1 × 0.1 = 0.0001
```

---

# Effect

- slow learning
- poor performance
- network cannot learn long dependencies

---

# Occurs In

- Deep neural networks
- Traditional RNNs

---

# Solution

1. ReLU activation
2. LSTM
3. Better initialization
4. Batch normalization

---

# (2) Exploding Gradient Problem

Gradients become extremely large.

Example:

```
10 × 10 × 10 = 1000
```

---

# Effect

- unstable training
- weights become huge
- model diverges

---

# Solution

Gradient clipping.

---

# (3) Overfitting

Model memorizes training data instead of learning patterns.

---

# Symptoms

- high training accuracy
- low testing accuracy

---

# Solutions

1. Dropout
2. More data
3. Regularization
4. Early stopping

---

# (4) High Computational Cost

Deep networks require:

- GPUs
- large memory
- long training time

---

# (5) Local Minima and Saddle Points

Optimization becomes difficult due to complex loss surface.

---

# 3. Activation Function

VERY IMPORTANT.

Without activation function:

- neural network behaves like linear model only.

Activation introduces nonlinearity.

---

# General Formula

y=f(x)y=f(x)y=f(x)

---

# Why Needed?

Activation functions:

1. introduce nonlinearity
2. help learn complex patterns
3. improve learning ability

---

# Types of Activation Functions

---

# (1) Sigmoid Function

Outputs between 0 and 1.

σ(x)=11+e−x\sigma(x)=\frac{1}{1+e^{-x}}σ(x)=1+e−x1​

---

# Properties

1. Smooth curve
2. Probabilistic interpretation
3. Used in binary classification

---

# Disadvantages

1. Vanishing gradient problem
2. Slow training

---

# (2) Tanh Function

Outputs between -1 and 1.

tanh⁡(x)=ex−e−xex+e−x\tanh(x)=\frac{e^x-e^{-x}}{e^x+e^{-x}}tanh(x)=ex+e−xex−e−x​

---

# Advantages

- zero centered
- better than sigmoid

---

# Disadvantages

Still suffers vanishing gradient.

---

# (3) ReLU (Most Important)

Rectified Linear Unit.

f(x)=max⁡(0,x)f(x)=\max(0,x)f(x)=max(0,x)

---

# Working

|Input|Output|
|---|---|
|Positive|Same value|
|Negative|0|

---

# Advantages

1. Fast computation
2. Reduces vanishing gradient
3. Most widely used

---

# Disadvantages

Dead neuron problem.

---

# (4) Softmax Function

Used in multiclass classification.

Converts outputs into probabilities.

---

# Difference Between Activation Functions

|Function|Range|Problem|
|---|---|---|
|Sigmoid|0 to 1|Vanishing gradient|
|Tanh|-1 to 1|Vanishing gradient|
|ReLU|0 to ∞|Dead neurons|

---

# 4. Evaluating ANN

Evaluation means measuring model performance.

---

# Common Evaluation Metrics

---

# (1) Accuracy

Accuracy=Correct PredictionsTotal PredictionsAccuracy=\frac{Correct\ Predictions}{Total\ Predictions}Accuracy=Total PredictionsCorrect Predictions​

---

# Example

90 correct predictions out of 100:

```
Accuracy = 90%
```

---

# (2) Precision

Measures correctness of positive predictions.

---

# (3) Recall

Measures ability to detect positives.

---

# (4) F1 Score

Balance between precision and recall.

---

# (5) Confusion Matrix

Table showing:

- true positives
- false positives
- true negatives
- false negatives
---

# 5. Improving and Tuning the ANN

This topic is very exam-oriented.

---

# Methods to Improve ANN

---

# (1) Better Activation Functions

Use:

- ReLU
- Leaky ReLU

instead of sigmoid.

---

# (2) Proper Learning Rate

Too high:

- unstable

Too low:

- slow training

---

# (3) Regularization

Prevents overfitting.

Examples:

- L1
- L2
- Dropout

---

# (4) Dropout

Randomly disables neurons during training.

Prevents memorization.

---

# (5) Batch Normalization

Normalizes inputs between layers.

Benefits:

1. Faster training
2. Stable learning
3. Better accuracy

---

# (6) More Training Data

Better generalization.

---

# (7) Early Stopping

Stops training before overfitting starts.

---

# 6. Hyperparameters vs Parameters

VERY COMMON EXAM QUESTION.

---

# Parameters

Parameters are learned automatically during training.

Examples:

- weights
- biases

---

# Hyperparameters

Hyperparameters are set manually before training.

Examples:

- learning rate
- epochs
- batch size
- number of layers

---

# Difference Table

|Feature|Parameters|Hyperparameters|
|---|---|---|
|Learned Automatically|Yes|No|
|Set Before Training|No|Yes|
|Examples|Weights, Biases|Learning rate|
|Optimization|During training|Manual tuning|

---

# 7. Greedy Layer Wise Training

Old but important deep learning technique.

---

# Idea

Instead of training whole network together:

- train one layer at a time.

---

# Steps

1. Train first layer
2. Freeze it
3. Train second layer
4. Continue sequentially

---

# Advantages

1. Easier optimization
2. Better initialization
3. Reduces training difficulty

---

# Disadvantages

1. Slow
2. Less common today

---

# 8. Recurrent Neural Networks (RNN)

VERY IMPORTANT.

---

# What is RNN?

RNN is a neural network designed for sequential data.

It remembers previous information using hidden states.

---

# Used For

1. Speech recognition
2. Language translation
3. Text prediction
4. Time series forecasting

---

# Key Feature

Has memory.

---

# Structure

```
Input → Hidden State → Output          ↑      Previous State
```

---

# Problem with RNN

Cannot remember long-term dependencies due to vanishing gradient.

---

# 9. Long Short-Term Memory (LSTM)

MOST IMPORTANT TOPIC.

---

# Why LSTM Introduced?

To solve vanishing gradient problem in RNNs.

---

# Key Idea

LSTM can remember information for long periods.

---

# Components of LSTM

1. Forget Gate
2. Input Gate
3. Output Gate
4. Cell State

---

# Forget Gate

Decides what information to remove.

---

# Input Gate

Decides what new information to store.

---

# Output Gate

Controls output generation.

---

# Advantages

1. Handles long-term dependencies
2. Better memory
3. Solves vanishing gradient

---

# Applications

1. Chatbots
2. Speech recognition
3. NLP
4. Time-series prediction
---

# 10. Gated Recurrent Unit (GRU)

GRU is simplified version of LSTM.

---

# Main Difference

GRU has:

- fewer gates
- simpler architecture
- faster training

---

# Gates in GRU

1. Update Gate
2. Reset Gate

---

# Advantages

1. Faster than LSTM
2. Less computation
3. Good performance

---

# Difference Between LSTM and GRU

|Feature|LSTM|GRU|
|---|---|---|
|Gates|3|2|
|Complexity|High|Lower|
|Speed|Slower|Faster|
|Memory|Better|Slightly lower|

---

# 11. Bidirectional RNN

Normal RNN:

- processes left → right only.

Bidirectional RNN:

- processes both directions.

---

# Advantage

Uses:

- past information
- future information

---

# Example

Sentence:

```
"The bank is near river"
```

Future words help understand meaning.

---

# 12. Bidirectional LSTM

Combines:

- LSTM
- bidirectional processing

---

# Advantages

1. Better context understanding
2. Improved sequence learning
3. Higher NLP accuracy

---

# Applications

1. Machine translation
2. Speech recognition
3. Sentiment analysis
---

# Quick Revision Notes

## Vanishing Gradient

- Gradients become tiny
- Early layers stop learning

## ReLU

- Most used activation
- Fast and efficient

## Hyperparameter

- Manually set

## Parameter

- Learned automatically

## RNN

- Sequential data processing

## LSTM

- Long-term memory
- Solves vanishing gradient

## GRU

- Simpler LSTM

## Bidirectional RNN

- Uses forward + backward context


# UNIT IV — Convolutional Neural Networks (CNN)

This is the most important scoring unit in deep learning.

Most exam papers heavily focus on:

- CNN architecture
- convolution operation
- pooling
- transfer learning
- famous architectures (AlexNet, ResNet, VGG)
- applications

If you understand CNN flow properly, you can answer almost every question in this unit.

---

# 1. Convolutional Neural Networks (CNN)

## What is CNN?

CNN is a type of deep neural network specially designed for:

- image processing
- computer vision
- pattern recognition

---

# Why CNN Was Introduced?

Traditional neural networks:

- cannot efficiently process images
- require huge parameters

CNN solves this by:

- local feature extraction
- parameter sharing
- convolution operation

---

# Basic Idea

CNN automatically learns:

- edges
- textures
- shapes
- objects

from images.

---

# Example

Suppose image contains cat.

CNN learns:

1. edges
2. ears
3. eyes
4. full cat structure

layer by layer.

---

# Main Applications

|Application|Use|
|---|---|
|Face Recognition|Security|
|Self-driving cars|Object detection|
|Medical Imaging|Tumor detection|
|OCR|Text recognition|
|Surveillance|Activity detection|

---

# Basic CNN Architecture

```
Input Image   ↓Convolution Layer   ↓Activation Function (ReLU)   ↓Pooling Layer   ↓Fully Connected Layer   ↓Output
```

---

# 2. Building Blocks of CNN

VERY IMPORTANT TOPIC.

---

# Main Building Blocks

1. Convolution Layer
2. Activation Function
3. Pooling Layer
4. Fully Connected Layer

---

# (1) Convolution Layer

Most important component.

---

# What is Convolution?

Convolution is operation where:

- small filter/kernel slides over image
- extracts important features

---

# Kernel / Filter

Small matrix like:

```
3×3 or 5×5
```

used to detect:

- edges
- patterns
- textures

---

# Example

Input image:

```
5 × 5 matrix
```

Kernel:

```
3 × 3 matrix
```

Kernel slides across image and produces:

- feature map

---

# Purpose

Extract features automatically.

---

# Advantages

1. Fewer parameters
2. Efficient computation
3. Feature extraction

---

# (2) Activation Function

Usually ReLU is used.

f(x)=max⁡(0,x)f(x)=\max(0,x)f(x)=max(0,x)

---

# Purpose

Adds nonlinearity.

Without activation:

- CNN becomes linear model only.

---

# (3) Pooling Layer

VERY IMPORTANT.

---

# What is Pooling?

Pooling reduces spatial size of feature maps.

---

# Why Needed?

1. Reduce computation
2. Reduce parameters
3. Prevent overfitting
4. Extract dominant features

---

# Types of Pooling

---

## (a) Max Pooling

Selects maximum value.

Example:

```
[1 3][2 4]
```

Output:

```
4
```

---

## (b) Average Pooling

Computes average value.

---

# Advantages of Pooling

1. Faster computation
2. Translation invariance
3. Noise reduction

---

# (4) Fully Connected Layer

Final layer in CNN.

Purpose:

- classification

---

# Working

Flattened feature maps connected to neurons.

Output example:

```
Cat = 95%Dog = 5%
```

---

# 3. Transfer Learning

VERY IMPORTANT MODERN TOPIC.

---

# What is Transfer Learning?

Transfer learning means:

- using pretrained model
- applying it to new task

---

# Example

Model trained on millions of images can be reused for:

- medical image detection
- face recognition

---

# Why Important?

Training CNN from scratch:

- expensive
- time consuming

Transfer learning saves:

- time
- computation
- data

---

# Steps

1. Use pretrained model
2. Freeze initial layers
3. Train final layers on new dataset

---

# Popular Pretrained Models

1. VGG
2. ResNet
3. Inception
4. MobileNet

---

# Advantages

1. Faster training
2. Less data required
3. Better accuracy

---

# 4. CNN Architectures

Very important for long questions.

---

# (1) LeNet

First successful CNN.

Developed by:  
Yann LeCun

---

# Purpose

Handwritten digit recognition.

---

# Features

1. 7-layer CNN
2. Used for digit classification
3. Introduced convolution + pooling

---

# Applications

Bank cheque recognition.

---

# (2) AlexNet

MOST IMPORTANT ARCHITECTURE.

Won ImageNet competition in 2012.

Developed by:  
Alex Krizhevsky

---

# Why Important?

Started deep learning revolution in computer vision.

---

# Features

1. Deep CNN
2. Uses ReLU
3. Uses dropout
4. GPU training

---

# Advantages

1. Higher accuracy
2. Faster training
3. Better feature extraction
---

# (3) VGG-16

Developed by:  
Visual Geometry Group

---

# Features

1. 16 layers
2. Uses small 3×3 filters
3. Deep architecture

---

# Advantages

1. Simple design
2. Good performance

---

# Disadvantages

1. Huge parameters
2. Slow training
---

# (4) ResNet

VERY IMPORTANT.

---

# Problem Solved

Very deep networks suffer:

- vanishing gradient
- degradation problem

ResNet introduced:

- skip connections

---

# Key Idea

Instead of learning:

```
H(x)
```

learn:

```
F(x) + x
```

---

# Residual Connection

Shortcut connection bypasses layers.

---

# Advantages

1. Very deep networks possible
2. Better accuracy
3. Easier training
---

# (5) Inception Network (GoogLeNet)

Designed by:  
Google

---

# Key Idea

Uses multiple filter sizes simultaneously.

Example:

- 1×1
- 3×3
- 5×5

in parallel.

---

# Advantages

1. Efficient computation
2. Multi-scale feature extraction

---

# Difference Between CNN Architectures

|Architecture|Main Feature|
|---|---|
|LeNet|First CNN|
|AlexNet|Deep CNN + ReLU|
|VGG-16|Very deep with small filters|
|ResNet|Skip connections|
|Inception|Parallel convolutions|

---

# 5. Applications in Vision, Speech and Audio-Video

Frequently asked theory question.

---

# (1) Vision Applications

CNN widely used in computer vision.

Examples:

1. Face recognition
2. Object detection
3. Image classification
4. Medical imaging
5. Autonomous vehicles

---

# (2) Speech Applications

CNN used in:

1. Speech recognition
2. Voice assistants
3. Speaker identification

Examples:

- Siri
- Alexa
- Google Assistant

---

# (3) Audio-Video Applications

Examples:

1. Video surveillance
2. Action recognition
3. Video recommendation
4. Audio classification

---

# Difference Between ANN and CNN

|Feature|ANN|CNN|
|---|---|---|
|Input|General data|Images|
|Feature Extraction|Manual|Automatic|
|Parameters|Huge|Reduced|
|Spatial Information|Lost|Preserved|

---

# Advantages of CNN

1. Automatic feature extraction
2. High image accuracy
3. Parameter sharing
4. Translation invariance

---

# Disadvantages

1. Requires large data
2. Computationally expensive
3. Needs GPUs

---
# Quick Revision Notes

## CNN

- Deep network for images

## Convolution

- Feature extraction using filters

## Pooling

- Reduces dimensions

## Transfer Learning

- Reusing pretrained model

## LeNet

- First CNN

## AlexNet

- Deep CNN with ReLU

## VGG-16

- 16-layer network

## ResNet

- Skip connections

## Inception

- Parallel convolutions

bp bbpt

You probably mean:

- **BP** = Backpropagation
- **BPTT / BBPT** = Backpropagation Through Time

People sometimes mistakenly write BBPT instead of BPTT.

---

# 1. BP — Backpropagation

Backpropagation is a training algorithm used in:

- Artificial Neural Networks (ANN)
- Multilayer Perceptrons (MLP)

It updates weights by propagating error backward.

---

# Main Idea

```
Prediction → Error → Weight Update
```

---

# Steps of Backpropagation

1. Forward propagation
2. Compute loss/error
3. Calculate gradients
4. Propagate error backward
5. Update weights

---

# Formula

wnew=wold−η∂L∂ww_{new}=w_{old}-\eta\frac{\partial L}{\partial w}wnew​=wold​−η∂w∂L​

Where:

- η = learning rate
- L = loss function

---

# Purpose

Reduce prediction error.

---

# Used In

- Feedforward Neural Networks
- MLPs
- CNNs

---

# Example

Image classification:

```
Predicted = DogActual = Cat
```

Backpropagation updates weights to reduce future error.

---

# 2. BPTT — Backpropagation Through Time

BPTT is extension of backpropagation used in:

- Recurrent Neural Networks (RNNs)

---

# Why Needed?

RNNs process sequential data:

- text
- speech
- time series

So error must flow through:

- multiple time steps

---

# Main Idea

RNN is “unrolled” across time.

Example:

```
x1 → h1 → y1      ↓x2 → h2 → y2      ↓x3 → h3 → y3
```

Error propagates backward through:

```
y3 → h3 → h2 → h1
```

---

# Why Called “Through Time”?

Because gradients move backward across:

- previous time states

---

# Applications

1. Language translation
2. Speech recognition
3. Chatbots
4. Text generation

---

# Problems in BPTT

1. Vanishing gradient
2. Exploding gradient
3. High computation cost

---

# Solution

LSTM and GRU were introduced.

---

# Difference Between BP and BPTT

|Feature|BP|BPTT|
|---|---|---|
|Used In|ANN/CNN|RNN|
|Data Type|Static data|Sequential data|
|Time Dependency|No|Yes|
|Error Propagation|Layer-wise|Time-wise|
