---
layout:     post
title:      "Flappy Bird Reinforcement Learning"
subtitle:   "Implementing Simple RL Algorithms to Play Flappy Bird"
date:       2023-09-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Reinforcement Learning
    - Game AI
    - Q-Learning
    - Deep Q-Network
    - Flappy Bird
    - Policy Gradient
    - RL Algorithms
---

> "Part of the Reinforcement learning course. The goal was to implement simple reinforcement learning algorithms to play Flappy Bird."

## Project Overview

Part of the Reinforcement learning course of [Stergios Christodoulidis](https://stergioc.github.io/). The goal was to implement simple reinforcement learning algorithms to play Flappy Bird.

## Game Visualization

![Flappy bird](https://raw.githubusercontent.com/clementw168/Flappy-Bird-RL/main/TFB_agent.gif)

## Technical Implementation

### Reinforcement Learning Framework
- **Environment**: Flappy Bird game environment
- **Agent**: RL agent learning to play the game
- **State Space**: Game state representation
- **Action Space**: Available actions (jump or not jump)
- **Reward Function**: Reward structure for learning

### Algorithm Implementations

#### 1. Q-Learning
- **Tabular Q-Learning**: Traditional Q-learning with state-action table
- **State Discretization**: Converting continuous game state to discrete states
- **Action Selection**: Epsilon-greedy policy for exploration vs exploitation
- **Q-Value Updates**: Updating Q-values based on experience

#### 2. Deep Q-Network (DQN)
- **Neural Network**: Using neural networks to approximate Q-function
- **Experience Replay**: Storing and replaying past experiences
- **Target Network**: Using separate target network for stability
- **State Representation**: Processing game screen as input

#### 3. Policy Gradient Methods
- **Policy Networks**: Direct policy optimization
- **REINFORCE**: Monte Carlo policy gradient algorithm
- **Actor-Critic**: Combining policy and value function learning
- **Advantage Estimation**: Using advantage functions for better learning

## Technical Details

### State Representation
- **Game Screen**: Raw pixel data from game
- **Feature Engineering**: Extracting relevant features from game state
- **State Normalization**: Normalizing state for stable learning
- **History**: Including temporal information in state

### Reward Design
- **Survival Reward**: Positive reward for staying alive
- **Distance Reward**: Reward based on distance traveled
- **Collision Penalty**: Negative reward for hitting obstacles
- **Sparse Rewards**: Handling sparse reward environments

### Training Process
- **Episode Management**: Managing training episodes
- **Exploration Strategy**: Balancing exploration and exploitation
- **Learning Rate**: Optimizing learning rate for stable training
- **Convergence**: Monitoring training progress and convergence

## Technical Stack

- **Reinforcement Learning**: Core RL algorithms and frameworks
- **Game Environment**: Flappy Bird game implementation
- **Neural Networks**: Deep learning for function approximation
- **Python**: Programming language for implementation

## Algorithm Comparison

### Q-Learning vs DQN
- **State Space**: Tabular vs continuous state representation
- **Scalability**: Handling large state spaces
- **Convergence**: Training stability and convergence speed
- **Performance**: Final performance comparison

### Policy Gradient vs Value-Based
- **Learning Approach**: Direct policy optimization vs value function learning
- **Sample Efficiency**: Data efficiency comparison
- **Stability**: Training stability differences
- **Exploration**: Exploration behavior differences

## Results and Performance

### Training Progress
- **Learning Curves**: Tracking performance over training episodes
- **Convergence**: Time to convergence for different algorithms
- **Final Performance**: Best performance achieved by each algorithm
- **Stability**: Training stability and variance

### Game Performance
- **Score Achievement**: Highest scores achieved
- **Consistency**: Performance consistency across runs
- **Generalization**: Performance on different game configurations
- **Robustness**: Handling of different game scenarios

## Documentation

### Full Report
[Complete Project Report](https://raw.githubusercontent.com/clementw168/Flappy-Bird-RL/main/report.pdf).

### Code Repository
[GitHub Repository](https://github.com/clementw168/Flappy-Bird-RL)

## Learning Outcomes

### Technical Skills
- **Reinforcement Learning**: Understanding core RL concepts and algorithms
- **Game AI**: Applying AI to game environments
- **Algorithm Implementation**: Implementing various RL algorithms
- **Performance Analysis**: Analyzing and comparing algorithm performance

### Reinforcement Learning Concepts
- **Markov Decision Processes**: Understanding MDP framework
- **Value Functions**: Learning about state and action value functions
- **Policy Optimization**: Understanding policy gradient methods
- **Exploration vs Exploitation**: Balancing exploration and exploitation

### Practical Experience
- **Environment Design**: Creating RL environments
- **Reward Engineering**: Designing effective reward functions
- **Hyperparameter Tuning**: Optimizing algorithm parameters
- **Debugging**: Troubleshooting RL training issues

## Challenges and Solutions

### Technical Challenges
- **State Representation**: Choosing effective state representation
- **Reward Design**: Creating reward functions that guide learning
- **Exploration**: Ensuring sufficient exploration for learning
- **Convergence**: Achieving stable and fast convergence

### Implementation Challenges
- **Environment Integration**: Integrating RL algorithms with game environment
- **Performance Optimization**: Optimizing training speed and efficiency
- **Debugging**: Debugging RL training and performance issues
- **Parameter Tuning**: Finding optimal hyperparameters

## Applications and Extensions

### Game AI
- **Other Games**: Applying RL to other game environments
- **Game Design**: Using RL for game testing and balancing
- **Player Modeling**: Understanding player behavior with RL
- **Procedural Content**: Generating game content with RL

### Real-World Applications
- **Robotics**: Applying RL to robotic control
- **Autonomous Systems**: Using RL for autonomous decision making
- **Resource Management**: Optimizing resource allocation with RL
- **Trading**: Applying RL to financial trading

## Future Directions

- Extension to more complex game environments
- Implementation of advanced RL algorithms
- Multi-agent reinforcement learning
- Real-world application development

## Tags

- **Reinforcement Learning**: Machine learning through interaction
- **Game AI**: Artificial intelligence in games
- **Q-Learning**: Value-based reinforcement learning algorithm
- **Deep Q-Network**: Deep learning for Q-function approximation
- **Flappy Bird**: Classic mobile game for AI testing
- **Policy Gradient**: Direct policy optimization methods
- **RL Algorithms**: Various reinforcement learning techniques
