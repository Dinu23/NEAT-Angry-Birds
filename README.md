# NEAT Angry Birds

## Overview

This project implements an AI agent to play a version of the classic Angry Birds game using a custom-built implementation of the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. NEAT is a genetic algorithm for evolving artificial neural networks, originally proposed by Kenneth O. Stanley. This implementation is built from the ground up to evolve neural networks that can effectively play Angry Birds by optimizing both the network topology and weights.

## Features

- **Custom NEAT Implementation**:
  - **From-Scratch Development**: NEAT is implemented from scratch, providing a deep understanding of its mechanics and allowing for custom modifications.
  - **Evolving Neural Networks**: Networks evolve in both topology and weight, creating increasingly complex and effective agents over time.
  - **Genetic Operations**: Includes mutation, crossover, and speciation to drive the evolution process.

- **Angry Birds Gameplay**:
  - **AI-Controlled Slingshot**: The AI aims to maximize its score by controlling the slingshot’s angle and power.
  - **Custom Game Environment**: Simulates the core mechanics of Angry Birds, providing a rich environment for training the AI.

## NEAT Algorithm Details

### Genome Representation

The genome in this implementation consists of two types of genes:

- **Node Genes**:
  - Unique ID
  - Type (input, bias, output, or hidden)
  - Activation function (e.g., ReLU, Sigmoid, Tanh)

- **Connection Genes**:
  - Input node ID
  - Output node ID
  - Connection weight
  - Enabled/disabled status
  - Innovation number, which uniquely identifies each connection and helps track its evolution over generations.

### Fitness Function

The fitness function is designed to evaluate how well a neural network controls the AI agent. It is defined as the mean score achieved by the agent across several attempts, reducing the variance and ensuring that the fitness reflects consistent performance rather than lucky runs.

### Mutation

The mutation process introduces small changes to the neural networks to explore new potential solutions. Key mutation operations include:

- Adding or removing connections.
- Adding or removing nodes.
- Adapting the weights of connections.
- Changing the activation functions of nodes.

### Crossover

The crossover operator combines the genomes of two parent networks to produce offspring. It distinguishes between common, disjoint, and excess genes, favoring the genes from the fitter parent while allowing for the inheritance of potentially beneficial mutations from both parents.

### Speciation

NEAT employs speciation to protect topological innovations and allow them time to evolve. The population is divided into species based on a similarity function that compares genomes, ensuring that innovative solutions are not prematurely eliminated due to competition with more established solutions.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Dinu23/NEAT-Angry-Birds.git
   ```

2. **Install the required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Training the AI

Run the training script to evolve the AI agent:

```bash
python train.py
```


## References

- [Original NEAT Paper by Kenneth O. Stanley](http://nn.cs.utexas.edu/downloads/papers/stanley.ec02.pdf)

