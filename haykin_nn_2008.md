# Introduction
## 1. What is a NN?
- A model of the brain implemented with computers
- Weights between neurons store the acquired knowledge
- Learning algorithms modify/update weights to attain a design objective
- Also possible for a NN to modify its topology

### Benefits of NN
- Parallel distributed structure
- Generalisation - production of reasonable outputs for inputs not seen during training
- Good for approximating solutions for *intractable* problems
    - Intractable problems - problems "slightly less than random" which have no efficient algorithm. The only algorithm that can solve them is the brute-force algorithm, and this is usually feasible only for the smallest of inputs. A truly random problem would have no algorithms that solves it.
1. Nonlinearity - The network's nodes can be non-linear which renders the entire network non-linear. This is suitable for non-linear problems (inputs) like speech.
2. Input-Output Mapping - The network is trained to map an input space to an output space. This is done without necessarily invoking a statistical model of the problem (input) apriori.
3. Adaptivity - The net can restructure itself to deal with continuous changes in the environment. This is useful in adaptive control, adaptive signal processing, adaptive classification, etc. However, one must find a good balance between the stability and plasticity of the network (small changes in environment leading to big changes in the network or vice-versa).
4. Evidential Response - The net can return probabilities (e.g. classification).
5. Contextual Information - Information is stored in the very structure and activation states of the neurons.
6. Fault Tolerance - If a neuron stops functioning correctly, the network's performance gracefully degrades (as opposed to a catastrophic failure in other types of systems).
7. VLSI Implementability - Very-large-scale-integrated technology potential due to its parallel network and, theferore, fast computation. It also captures complex behaviour in a highly hierarchical fashion.
8. Uniformity of Analysis and Design - The unit of a network is the neuron. This is used in most networks. The same notation is used accross the board, making it easy to share theories and ideas. It also allows for modular networks to combine different types of neurons and layers of neurons.
9. Neurobiological Analogy - ANNs inspire and are inspired by neurobiology.

## 2. The human brain
- 10 billion neurons, 60 trillion synapses
- Stimulus -> Receptors <-> Neural Net <-> Effectors -> Response
- Structural organisation in the brain: Molecules > Synapses > Neural microcircuits > Dendritic trees > Neurones > Local circuits > Interregional circuits > Central nervous system
- Different types of cells specialised for different functions, in different areas of the brain
- ANNs are rudimentary compared to the brain, but much progress is being made

## 3. Models of a neuron
1. Set of weighted synapses
2. Adder - sums up the weighted input signals to give the *induced local field*
3. Activation function - function of the induced local field mapping to a bounded interval (e.g.\[-1, 1\])

### Types of activation function
#### 1. Threshold function
#### 2. Sigmoid function

### Stichastic model of a neuron
- For some applications it may be useful to have a stochastic neural model.
- We can have a probabilistic interpretation of the McCulloch-Pitts model by introducing noise, making the neuron non-deterministic.

## 4. Neural networks viewed as directed graphs
NNs can be seen as:
1. Block diagrams - a functional description of the net
2. Architectural graph - describing the network layout
3. Signal-flow graph - a complete description of signal flow in the network

## 5. Feedback
- When the output of a neuron influences its input
- Closed-feedback loops can be unfolded
- Feedback loops can be stable, linearly divergent or exponentially divergent

## 6. Network architectures
- Single-layer feedforward networks - input layer and output(computational) layer
- Multilayered feedforward networks - multiple hidden(computational) layers (containing hidden neurons). "i-h1-h2-...-hn-o network". Can be fully or partially connected (if the neurons in one layer are connected to all neurons in the forward layer or not)
- Recurrent networks - contains feedback loops. These feedback loops can be self-feedback loops or not. The feedback loops use unit-time delay elements (denoted by `z^(-1)`)

## 7. Knowledge representation
- Prior knowledge - Weights and biases represent the state of the environment
- Examples - used to train the neural network to better represent the world state. Examples can be labelled, unlabelled, positive or negative.
- A network architecture is chosen, it is then trained and tested. Good performance in testing is called generalisation.

### Rules of knowledge representation
1. Similar inputs from similar classes should produce similar representations inside the network, and should therefore be classified as belonging to the same class. We can use the Euclidean distance between vectors, the cosine angle between vectors or the dot product of vectors (projecting one onto the other).
2. Items to be categorised in separate classes should be given widely different representations in the network
3. If a feature is particularly important, there should be a large number of neurons representing that feature in the network
4. Prior information and invariances should be built into the design of a neural network when they are available, so as to simply the network design by its not having to learn them.

### How to build prior information into neural network design
1. restricting network architecture through the use of local connections a.k.a. *receptive fields*
2. constrain the choice of synaptic weights through the use of *weight-sharing*(using the same weight vector to do the *convolution*)

### How to build invariances into neural network design
- E.g. if an image is rotated, the classifier should classify it as being part of the same class.
- Some techniques for making classifier neural nets *invariant* to *transformations*:
#### 1. Invariance by structure
- enforcing structural design choices
- can lead to very large networks
#### 2. Invariance by training
- train the network with examples of transformations
- con: novel transformations might not be trained for
- con: learning all of the transformation might be computationally overwhelming for the network
### 3. Invariant feature space
- input -> INVARIANT FEATURE EXTRACTOR -> CLASSIFIER NEURAL NETWORK -> class estimate
- unburden the classifier network of having to deal with transformations

## 8. Learning processes

### Learning with a teacher (supervised learning)
- The teacher tries to train the network with its own knowledge
- The teacher provides input-output examples to the network
- The network learns using the input vector and the error - the difference between the desired output and the actual output
- Once a statistically optimum is reached, the network is said to have learnt to emulate the teacher
- The knowledge is now said to be encoded in the structure of the network (its weights) as long-term memory
- This can also be thought of as an error surface, with the network trying to find a local or global minima on the surface

### Learning without a teache

#### 1. Reinforcement learning
- learning to perform a task on the basis of the outcomes of its interaction with the environment.
- the learning system and the environment are part of the feedback-loop
- the system is build around a *critic* that converts *primary reinforcement signal* from the environment into a higher quality signal called the *heuristic reinforcement signal*

#### 2. Unsupervised learning
- system tries to optimise a task-independent measure, creating its own classes

## 9. Learning tasks

### Pattern association
- Autoassociation - NN is required to *store* a set of patterns by repeatedly presenting them to the network. Unsupervised.
    - The network should correctly classify a newly presented partial or noisy pattern.
    - Storage phase and Recall phase
    - Error in recall
    - The number of patterns stored in the network is the *storage capacity* of the network. Ideally this is maximised while still correctly classifying many patterns.
- Heteroassociation - arbitrary set of input patterns associated with an arbitrary set of output patterns. Supervised

### Pattern recognition
- a received pattern is assigned to one of the classes.
- pattern recognition is statistican in nature, patterns being represented by points in a multidimensional *decision space*. The decision space is divided into regions separated by decision boundaries.
- The decision boundaries are determined during training.
- Pattern recognition can be split into
    - feature extraction and
    - classification
- The steps above can be separated into two networks, or can be done by only one network.

### Function approximation
- System identification
- Inverse modelling

### Control

### Beamforming
