---
layout:     post
title:      "Prey Predator Simulation with MADDPG"
subtitle:   "Multi-Agent Reinforcement Learning for Cooperative Behavior"
date:       2024-04-01 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/cs-mva/maddpg.gif"
catalog: true
published: true
tags:
    - Student project
    - Reinforcement Learning
    - Deep Learning
    - Multi-Agent Learning
    - MADDPG
pride_score: 1
---

## Project Overview

This project simulates a prey-predator ecosystem using **multi-agent reinforcement learning**. We apply the **Multi-Agent Deep Deterministic Policy Gradient (MADDPG)** algorithm to learn cooperative behaviors among predators while preys try to escape.  

The environment is a 2D world where multiple species interact dynamically: predators hunt, preys evade, and some species can even be both. This setup reflects the complexity of real ecosystems, where survival depends on both competition and cooperation.  

![Demo gif](https://raw.githubusercontent.com/clementw168/prey-predator-rl/main/assets/demo.gif)  
![Poster](/img_compressed/posts/cs-mva/maddpg_poster.jpg)  


## Technical Approach

### Environment
Agents move in a 2D plane with either borders or a looping torus. Species are assigned predator/prey roles, with interactions determined by distances. Complex food chains can be modeled where a species is predator to one group and prey to another.

### Observations & Actions
Each agent observes relative positions of others plus its past action. Actions are continuous 2D vectors in \[-1,1\], defining movement directions scaled by species speed.

### Rewards
The reward system balances survival and cooperation:  
- **Predator catching prey:** +10  
- **Prey captured:** -10  
- **Evasion:** reward proportional to distance from predators  
- **Cooperation:** shared reward for minimizing team distance to prey  
- **Borders:** penalties when crossing limits if borders are enabled

Episodes end when all preys are caught or after a fixed number of steps.

### Algorithm: MADDPG
We use **centralized training, decentralized execution**:  
- Each agent has its own actor network (policy).  
- A centralized critic uses states and actions of all agents to evaluate Q-values.  
- Replay buffers and target networks stabilize training.  

To model species invariance, we also experimented with **shared networks** across agents of the same species. While promising, this introduced training instability due to conflicting gradients from agents with different experiences.


## Some insights

- With individual rewards, predators acted selfishly, failing to cooperate.  
- Adding **shared rewards** encouraged coordination, leading to successful captures.  
- Complex food chains generated chaotic but realistic dynamics, highly sensitive to agent initializations.  
- Modeling the world as a torus made prey escape easier, highlighting how geometry influences emergent strategies.  
- Shared networks for species improved representation capacity but slowed convergence due to unstable credit assignment. 

More details can be found in the [report](https://raw.githubusercontent.com/clementw168/prey-predator-rl/main/report.pdf) and the [poster](https://raw.githubusercontent.com/clementw168/prey-predator-rl/main/assets/poster.pdf).


## Documentation

- 📑 [Full Report](https://raw.githubusercontent.com/clementw168/prey-predator-rl/main/report.pdf)  
- 💻 [GitHub Repository](https://github.com/clementw168/prey-predator-rl)  
- 🎨 [Poster Presentation](https://raw.githubusercontent.com/clementw168/prey-predator-rl/main/assets/poster.pdf)  


## References
1. Lillicrap, T.P., et al. (2015). Continuous control with deep reinforcement learning. *arXiv:1509.02971*.  
2. Lowe, R., et al. (2017). Multi-agent actor-critic for mixed cooperative-competitive environments. *NeurIPS 30*.  
