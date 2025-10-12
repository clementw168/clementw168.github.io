---
layout:     post
title:      "Spiking Neural Networks Benchmark"
subtitle:   "Exploring Bio-Inspired Computing for Image and Time Series Classification"
date:       2023-09-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/cs-mva/snn.png"
header-mask: 0.3
catalog: true
published: true
tags:
    - Student project
    - Deep Learning
    - Spiking Neural Networks
---


## Project Overview

This was a one-week project exploring **Spiking Neural Networks (SNNs)**—a bio-inspired neural network paradigm that mimics the behavior of biological neurons. The work was conducted in collaboration with **Timothée Masquelier**, allowing us to dive deeper into SNN dynamics and learning mechanisms. Unlike traditional artificial neural networks (ANNs) that process continuous values, SNNs transmit information via discrete **spikes**, capturing not only input magnitude but also precise timing.  

We focused on understanding how SNNs work, their unique learning mechanisms, and how to implement them for image and time series tasks.  

![Spiking NN basics](https://raw.githubusercontent.com/clementw168/Spiking-Neural-Networks-Benchmark/main/assets/LIF_model.png)

## How Spiking Neural Networks Work

### 1. Biological Inspiration
SNNs are inspired by the brain, where neurons communicate through **action potentials** (spikes). A neuron integrates incoming signals from other neurons until its **membrane potential** exceeds a threshold, at which point it fires a spike. This spike travels along the axon, possibly with delays controlled by myelin insulation, and influences downstream neurons.

### 2. Leaky Integrate-and-Fire (LIF) Model
The **Leaky Integrate-and-Fire (LIF) neuron** is a simplified model of a biological neuron:

- **Integration**: Incoming spikes increase the neuron’s membrane potential.  
- **Leakage**: The potential decays over time, mimicking natural membrane leakage.  
- **Firing**: When the potential exceeds a threshold, the neuron emits a spike and resets.  

This model captures essential neuronal dynamics while remaining computationally feasible. It allows SNNs to process temporal information in a way that traditional ANNs cannot.

### 3. Learning in SNNs
Training SNNs poses unique challenges due to the **non-differentiable spike function**. Standard backpropagation cannot compute gradients through discrete spikes. Two key solutions are used:

- **Surrogate Gradient Learning**: Replaces the non-differentiable spike function with a smooth approximation (e.g., a sigmoid) during gradient computation, allowing standard gradient-based optimization.  
- **Delay Learning**: Synaptic delays between neurons can be learned during training, enabling the network to capture precise temporal relationships in data. Delays are represented as Gaussian kernel convolutions whose mean shifts during training, effectively shaping the spike timing.

These mechanisms allow SNNs to encode temporal patterns and event-based information naturally.

### 4. Temporal Computation
SNNs process information over time rather than in a single forward pass:

- Neurons integrate spikes across multiple timesteps.  
- The timing of spikes carries information, making SNNs well-suited for **time series** or **sensor-based data**.  
- Temporal coincidences of spikes from multiple neurons can trigger specific patterns in downstream neurons, encoding complex temporal relationships.

### 5. Advantages and Use Cases
SNNs excel in scenarios where timing is critical or data is **event-driven**, such as:

- Speech and audio processing  
- Human activity recognition  
- Neuromorphic hardware applications  
- Real-time sensor networks  

Compared to ANNs, SNNs can reduce energy consumption when implemented on specialized hardware because neurons are mostly inactive unless they spike.

## Reflections

This project allowed me to explore the inner workings of SNNs and understand how biological principles can inspire novel machine learning approaches. While SNNs are slower to train and currently less effective for image classification than CNNs, their temporal capabilities make them highly promising for sequential and event-based data.

For detailed implementation, code examples, and experiments, see the [GitHub repository](https://github.com/clementw168/Spiking-Neural-Networks-Benchmark).  

## References

1. Maass, W. (1997). *Networks of spiking neurons: the third generation of neural network models.* Neural networks, 10(9), 1659-1671.  
2. Maass, W., & Schmitt, M. (1999). *On the complexity of learning for spiking neurons with temporal coding.* Information and Computation, 153(1), 26-46.  
3. Tavanaei, A., et al. (2019). *Deep learning in spiking neural networks.* Neural networks, 111, 47-63.  
4. Neftci, E. O., et al. (2019). *Surrogate gradient learning in spiking neural networks.* IEEE Signal Processing Magazine, 36(6), 51-63.  
5. Hammouamri, I., et al. (2023). *Learning Delays in Spiking Neural Networks using Dilated Convolutions with Learnable Spacings.* arXiv preprint arXiv:2306.17670.
