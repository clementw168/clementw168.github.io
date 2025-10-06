---
layout:     post
title:      "Implicit Acceleration by Overparameterization"
subtitle:   "Reimplementing Experiments from the Paper"
date:       2024-02-15 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/cs-mva/linear_equivalence_dark.png"
catalog: true
published: true
tags:
    - Optimization
    - Deep Networks
    - Theory
    - Research Implementation
    - Course Project
---

## Project Overview

This project was part of the [Theoretical Principles of Deep Learning course](https://hedi-hadiji.github.io/tdl-page/intro.html) taught by Hedi Hadiji.  
Together with Guillaume Levy, I reimplemented the experiments of the paper:  

**Arora, S., Cohen, N., & Hazan, E. (2018).**  *On the Optimization of Deep Networks: Implicit Acceleration by Overparameterization.*  Proceedings of ICML 2018. [arXiv:1802.06509](https://arxiv.org/abs/1802.06509)

The central idea of the paper is **counterintuitive**: increasing the depth of a neural network—even when using *linear* layers only can accelerate training (so adding layers without non-linearities). This effect is not due to added expressiveness (since stacked linear layers are equivalent to a single one), but rather emerges from how **optimization dynamics** change when the network is overparameterized.

## Theoretical Background

Consider a network of depth *N* with only linear layers and no activations. In function space, this is equivalent to a single linear transformation.

![Linear network](/img/posts/cs-mva/linear_equivalence.png)


Despite functional equivalence, the optimization trajectory differs. When training each layer with SGD, the equivalent one-layer model effectively inherits:
  - An **adaptive learning rate** depending on weight norms.  
  - A form of **implicit momentum**, coming from how gradients propagate through layers.  

These properties are not introduced by hand (like with Adam or momentum SGD), but arise naturally from depth. This is why the phenomenon is called **implicit acceleration**.

See the full proof in the [report](https://raw.githubusercontent.com/clementw168/Implicit-acceleration-by-overparametrization/main/assets/report.pdf).


## Experiments

To test these ideas, we trained networks with **1, 2, and 3 linear layers** on two datasets:

- **Gas Sensor Array Dataset** (ethanol concentration prediction)  
- **Abalone Dataset** (predicting age from physical features)

Key aspects of our experimental setup:
- Grid search over learning rates to isolate convergence effects.  
- Comparison of different **initializations**: near-zero vs. near-identity matrices.  
- Comparison with **other optimizers** such as Adam.  

### Observations
- Results were highly dependent on initialization and dataset.  
- In some cases, deeper linear networks converged faster (supporting the theory).  
- In others, a simple one-layer model or Adam optimizer outperformed.  
- Overparameterization occasionally introduced instability (“bursts” in training loss).  

![Learning curves](https://raw.githubusercontent.com/clementw168/Implicit-acceleration-by-overparametrization/main/assets/learning_curves.png)


## Takeaways

- **Theory vs. Practice**: While the math suggests a universal implicit acceleration effect, in practice the results depend heavily on initialization, optimizer choice, and dataset.  
- **Key insight**: Depth does not only affect *expressiveness* of neural networks—it also changes the **optimization landscape** in subtle ways.  
- **Open question**: How far can implicit acceleration go compared to explicitly designed optimizers like Adam or momentum-SGD?  


## Resources

- 📄 [Full Project Report (PDF)](https://raw.githubusercontent.com/clementw168/Implicit-acceleration-by-overparametrization/main/assets/report.pdf)  
- 🎤 [Presentation Slides](https://raw.githubusercontent.com/clementw168/Implicit-acceleration-by-overparametrization/main/assets/slides.pdf)  
- 💻 [GitHub Repository](https://github.com/clementw168/Implicit-acceleration-by-overparametrization)  

---

## Final Thoughts

Our experiments did not align with the paper's results. Since the paper was published at ICML, we would have expected the results to be accurate and consistant. Looking at other projects from the course, it seemed that it was pretty common that results differed from the papers. Since the paper is rather simple, I do not think that our experiments were wrong. It made me wonder how much we can trust the results of papers.
