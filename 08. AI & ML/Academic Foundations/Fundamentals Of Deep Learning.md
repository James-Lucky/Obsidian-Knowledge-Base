##### **UNIT - 2** (Introduction to Neural Network)

**Introduction to Neural Network** - A neural network is ==a machine learning model inspired by the human brain==. It uses layers of interconnected "neurons" to process data, allowing computers to recognize complex patterns, make decisions, and learn from experience without needing strict, pre-defined rules. 

-**How They Work:** Neural networks break down complex problems by passing information through three primary types of layers:

- **Input Layer:** Receives the raw data (like individual pixels in an image or values in a spreadsheet) and passes it to the network.
- **Hidden Layers:** The core processing engine. They consist of layers of nodes that perform mathematical transformations to recognize abstract patterns and features.
- **Output Layer:** Produces the final result, such as a prediction, a classification (e.g., "This is a cat"), or a decision. 

**-Core Concepts:** To map inputs to outputs, a neural network relies on a few key components:

- **Weights:** Numerical values that determine the strength of the connection between neurons. The network adjusts these weights over time based on training data to improve accuracy.
- **Biases:** Constants added to neurons that give the model the flexibility to adjust the final output.
- **Activation Functions:** Mathematical rules that determine whether a neuron "fires" or passes its signal to the next layer, adding the necessary complexity to handle non-linear relationships. 

**-Common Types & Uses:**

- **Deep Neural Networks (DNN):** The foundational technology behind "deep learning," which involves many hidden layers to tackle massive, unstructured datasets.
- **Convolutional Neural Networks (CNN):** Specialized for processing visual data, making them the backbone of computer vision and image recognition.
- **Transformers:** Advanced architectures that power today's large language models (LLMs) and natural language processing (NLP) to generate text and translate languages.
# Why Neural Networks are Powerful?

Because they can:
- learn nonlinear patterns
- approximate complex functions
- automatically learn features

# Applications

|Application|Use|
|---|---|
|Face Detection|Security|
|Speech Recognition|Voice assistants|
|Medical Diagnosis|Disease detection|
|NLP|Chatbots|
|Recommendation Systems|Netflix, YouTube|
![[Pasted image 20260525171650.png]]


### 2. Biological Neuron in Neural Network:

A biological neuron is ==the fundamental, information-processing unit of the nervous system==. It serves as the primary structural and functional inspiration for [Artificial Neural Networks (ANNs)](https://www.geeksforgeeks.org/machine-learning/difference-between-ann-and-bnn/), translating electrical and chemical signals to facilitate learning, memory, and cognitive decision-making. 

**Core Biological Components:**

A biological neuron manages information through four main structural parts:
- **Dendrites:** Tree-like branches that act as "antennas," receiving electrochemical signals from neighboring neurons.
- **Soma (Cell Body):** The central processing unit that integrates and sums the incoming signals.
- **Axon:** A long, cable-like projection that transmits the processed electrical signal (action potential) away from the soma.
- **Synapses:** The microscopic gaps and connection points between the axon terminals of one neuron and the dendrites of another. Neurotransmitters carry the signal across this gap.

**How They Work**:
Neurons operate via an "all-or-nothing" threshold system. When the total electrical input received at the dendrites and processed by the soma exceeds a specific threshold, the neuron **fires**. This sends a wave of electrical activity down the axon. 

**The Biological vs. Artificial Connection**:

Artificial neural networks mimic this biological architecture, translating organic processes into mathematical operations:

- **Input (Dendrites):** The data or features fed into an artificial neuron.
- **Weights (Synapses):** The numerical values that adjust the importance of an input, mimicking synaptic strength.
- **Weighted Sum (Soma):** The calculation of all inputs multiplied by their respective weights.
- **Activation Function (Firing Threshold):** A mathematical formula (such as ReLU or Sigmoid) that determines if the artificial neuron outputs a signal to the next layer. 

[![[Pasted image 20260525181357.png](https://media.geeksforgeeks.org/wp-content/uploads/20260424070509198897/annbnn.webp)
