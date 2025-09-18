---
layout:     post
title:      "Improving Nash Equilibrium Finding Algorithm Convergence with Google DeepMind"
subtitle:   "Population-Based Ideas for Faster FoReL Algorithm Convergence"
date:       2024-04-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Game Theory
    - Nash Equilibrium
    - DeepMind
    - Research
    - Optimization
    - FoReL
    - Multi-Agent Learning
---

> "Working with Google DeepMind to improve convergence speed of FoReL-based algorithms using population-based ideas for two-player zero-sum games."

![DeepMind banner](/img/pages/DeepMind.png)

## Project Overview

During my last year at CentraleSupélec, I had the opportunity to work with Google DeepMind on a research project from October 2023 to April 2024. The goal was to improve the convergence speed of FoReL (Follow the Regularized Leader) based algorithms with population-based ideas.

## Research Focus

### Problem Statement
- Traditional FoReL algorithms can be slow to converge to Nash equilibria
- Population-based methods show promise for improving convergence in multi-agent settings
- Two-player zero-sum normal form games provide a good testbed for algorithm development

### Our Approach
We designed an algorithm that combines FoReL with population-based ideas to achieve faster convergence to Nash equilibria in two-player zero-sum games.

## Algorithm Design

![Algorithm](https://raw.githubusercontent.com/tboulet/Algorithms-for-Normal-Form-Games/main/assets/mp_b_palforel.png)

### Key Innovations
- **Population-Based FoReL**: Integrated population dynamics with FoReL updates
- **Multi-Point Optimization**: Maintained multiple solution candidates simultaneously
- **Adaptive Learning Rates**: Dynamically adjusted learning parameters based on population diversity

### Technical Implementation
- Developed novel update rules combining FoReL with population-based selection
- Implemented efficient algorithms for maintaining population diversity
- Created robust convergence criteria for multi-agent settings

## Results

### Performance Improvements
- **Significant Speedup**: Achieved substantial gains in convergence speed
- **Robust Performance**: Consistent improvements across different game types
- **Scalability**: Algorithm performed well on various game sizes

### Validation
- Tested on multiple two-player zero-sum normal form games
- Compared against standard FoReL implementations
- Demonstrated consistent convergence improvements

## Technical Details

### Game Theory Foundation
- **Nash Equilibrium**: Theoretical foundation for solution concepts
- **Zero-Sum Games**: Mathematical framework for competitive scenarios
- **Normal Form Games**: Standard representation for strategic interactions

### Algorithm Components
- **FoReL Updates**: Regularized leader following for strategy updates
- **Population Dynamics**: Multi-agent evolution for solution diversity
- **Convergence Analysis**: Theoretical guarantees for algorithm performance

## Documentation and Resources

### Full Report
[Complete Project Report](https://raw.githubusercontent.com/tboulet/Algorithms-for-Normal-Form-Games/main/Project%20report.pdf)

### Code Repository
[GitHub Repository](https://github.com/tboulet/Algorithms-for-Normal-Form-Games)

## Impact and Learning

### Research Experience
- Collaborated with world-class researchers at Google DeepMind
- Gained experience in cutting-edge game theory and optimization research
- Developed skills in theoretical analysis and experimental validation

### Technical Skills
- Advanced game theory and Nash equilibrium concepts
- Population-based optimization algorithms
- Multi-agent learning and convergence analysis
- Research methodology and academic writing

## Future Directions

- Extension to more complex game types beyond zero-sum
- Application to real-world multi-agent scenarios
- Integration with deep reinforcement learning methods
- Theoretical analysis of convergence guarantees

## Tags

- **Game Theory**: Mathematical framework for strategic decision making
- **Nash Equilibrium**: Core solution concept in game theory
- **DeepMind Research**: Collaboration with leading AI research lab
- **Optimization**: Algorithm design for faster convergence
- **Multi-Agent Learning**: Learning in competitive environments
- **FoReL**: Follow the Regularized Leader algorithm family
- **Population-Based Methods**: Evolutionary approaches to optimization
