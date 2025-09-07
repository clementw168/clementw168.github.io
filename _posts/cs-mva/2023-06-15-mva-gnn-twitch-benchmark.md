---
layout:     post
title:      "Graph Neural Network Benchmark on Twitch Dataset"
subtitle:   "Benchmarking Different GNN Architectures on Multiple Classification and Regression Tasks"
date:       2023-06-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Graph Neural Networks
    - GNN
    - Benchmarking
    - Twitch Dataset
    - Classification
    - Regression
    - Network Science
---

> "The goal was to benchmark different architectures on the Twitch dataset on several classification and regression tasks."

## Project Overview

Part of the [Machine Learning on Network Science course](https://fragkiskos.me/teaching/MLNS-S22/) of Fragkiskos Malliaros. The goal was to benchmark different architectures on the Twitch dataset on several classification and regression tasks.

## Learning Curves Visualization

![Learning curves](https://raw.githubusercontent.com/clementw168/mlns_twitch_project/main/assets/learning_curves.png)

## Technical Implementation

### Graph Neural Network Architectures
- **Graph Convolutional Networks (GCN)**: Basic graph convolution operations
- **Graph Attention Networks (GAT)**: Attention-based graph neural networks
- **GraphSAGE**: Inductive representation learning on large graphs
- **Graph Transformer**: Transformer-based graph neural networks

### Benchmark Tasks
- **Node Classification**: Classifying nodes based on graph structure and features
- **Link Prediction**: Predicting missing edges in the graph
- **Graph Classification**: Classifying entire graphs
- **Regression Tasks**: Predicting continuous values for nodes or graphs

### Twitch Dataset
- **Social Network**: Twitch user interaction network
- **Node Features**: User attributes and characteristics
- **Edge Information**: User relationships and interactions
- **Task Labels**: Various classification and regression targets

## Technical Details

### Model Architectures
- **GCN**: Standard graph convolutional layers with message passing
- **GAT**: Multi-head attention mechanisms for graph learning
- **GraphSAGE**: Neighborhood sampling and aggregation strategies
- **Custom Architectures**: Experimenting with novel GNN designs

### Training Configuration
- **Optimization**: Adam optimizer with appropriate learning rates
- **Regularization**: Dropout, weight decay, and other regularization techniques
- **Validation**: Cross-validation and hold-out validation strategies
- **Hyperparameter Tuning**: Systematic hyperparameter optimization

### Performance Evaluation
- **Metrics**: Accuracy, F1-score, AUC, and regression metrics
- **Cross-Validation**: Robust performance evaluation across data splits
- **Statistical Significance**: Testing for statistically significant differences
- **Error Analysis**: Analyzing model errors and failure cases

## Results and Analysis

### Architecture Comparison
- **Performance Ranking**: Ranking different GNN architectures by performance
- **Task-Specific Performance**: Performance on different types of tasks
- **Scalability Analysis**: Performance vs computational complexity
- **Convergence Analysis**: Training stability and convergence speed

### Learning Curves
- **Training Progress**: Tracking training and validation performance over time
- **Overfitting Analysis**: Identifying overfitting and underfitting patterns
- **Convergence Behavior**: Understanding convergence characteristics
- **Performance Stability**: Assessing training stability across runs

## Documentation

### Full Report
[Complete Project Report](https://raw.githubusercontent.com/clementw168/mlns_twitch_project/main/assets/report.pdf).

### Code Repository
[GitHub Repository](https://github.com/clementw168/mlns_twitch_project)

## Learning Outcomes

### Technical Skills
- **Graph Neural Networks**: Understanding GNN architectures and principles
- **Graph Learning**: Learning from graph-structured data
- **Benchmarking**: Systematic comparison of different approaches
- **Network Science**: Understanding network analysis and graph theory

### GNN Concepts
- **Message Passing**: Understanding message passing in graph neural networks
- **Node Embeddings**: Learning node representations in graph space
- **Graph Convolution**: Convolution operations on graph data
- **Attention Mechanisms**: Attention-based graph learning

### Research Experience
- **Experimental Design**: Designing comprehensive benchmarking studies
- **Performance Analysis**: Analyzing and comparing model performance
- **Statistical Analysis**: Statistical evaluation of experimental results
- **Academic Writing**: Documenting research findings and analysis

## Technical Innovation

### Benchmarking Methodology
- **Comprehensive Evaluation**: Systematic evaluation across multiple architectures
- **Multiple Tasks**: Testing on various classification and regression tasks
- **Statistical Rigor**: Ensuring statistically significant comparisons
- **Reproducibility**: Creating reproducible experimental setups

### GNN Analysis
- **Architecture Comparison**: Detailed comparison of different GNN approaches
- **Task Suitability**: Understanding which architectures work best for which tasks
- **Performance Analysis**: Deep analysis of performance characteristics
- **Scalability Assessment**: Evaluating computational efficiency

## Applications and Extensions

### Research Applications
- **Graph Learning Research**: Contributing to graph neural network research
- **Architecture Design**: Informing design of new GNN architectures
- **Task-Specific Optimization**: Optimizing architectures for specific tasks
- **Benchmarking Standards**: Establishing benchmarking standards for GNNs

### Practical Applications
- **Social Network Analysis**: Analyzing social networks and user behavior
- **Recommendation Systems**: Building recommendation systems on graph data
- **Fraud Detection**: Detecting fraudulent behavior in networks
- **Drug Discovery**: Applying GNNs to molecular and biological networks

## Challenges and Solutions

### Technical Challenges
- **Graph Heterogeneity**: Handling heterogeneous graph structures
- **Scalability**: Scaling GNNs to large graphs
- **Overfitting**: Preventing overfitting in graph learning
- **Hyperparameter Sensitivity**: Managing hyperparameter sensitivity

### Experimental Challenges
- **Fair Comparison**: Ensuring fair comparison between architectures
- **Computational Resources**: Managing computational requirements
- **Reproducibility**: Ensuring reproducible experimental results
- **Statistical Analysis**: Proper statistical analysis of results

## Future Directions

- Extension to more GNN architectures
- Application to different graph datasets
- Development of new benchmarking methodologies
- Integration with other machine learning approaches

## Tags

- **Graph Neural Networks**: Deep learning for graph-structured data
- **GNN**: Graph Neural Networks abbreviation
- **Benchmarking**: Systematic comparison of different approaches
- **Twitch Dataset**: Social network dataset for graph learning
- **Classification**: Supervised learning for categorical prediction
- **Regression**: Supervised learning for continuous prediction
- **Network Science**: Scientific study of networks and graphs
