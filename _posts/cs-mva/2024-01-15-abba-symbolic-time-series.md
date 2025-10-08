---
layout:     post
title:      "Implementation of ABBA Symbolic Representation of Time Series"
subtitle:   "Adaptive Brownian Bridge-based Symbolic Aggregation for Time Series Forecasting"
date:       2024-01-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/cs-mva/sunspot_results_dark.png"
catalog: true
published: true
tags:
    - Time Series
    - Symbolic Representation
    - ABBA
    - LSTM
    - Forecasting
    - Machine Learning
---

## Project Overview

This project was part of the [Machine Learning for Time Series course](http://www.laurentoudre.fr/ast.html) by Laurent Oudre. Together with Guillaume Levy, I reimplemented two papers on symbolic representations of time series, focusing on the **ABBA method** (Adaptive Brownian Bridge-based symbolic Aggregation).

Our objectives were:  
1. Understand how ABBA compresses and encodes time series.  
2. Evaluate whether ABBA representations can be combined with LSTMs for forecasting, compared to raw time series baselines.  


## Why Symbolic Representations?

Time series often pose challenges for deep learning: they are long, noisy, and contain redundant patterns. Symbolic representations like ABBA attempt to **compress a signal into a sequence of discrete symbols**, preserving its key dynamics while reducing dimensionality.  

Potential benefits include:  
- Lower computational cost for training and inference  
- Improved interpretability of recurring patterns  
- A bridge between symbolic analysis and modern deep learning models  


## The ABBA Method

ABBA converts a time series into symbols through three main stages:

1. **Segmentation** – The signal is approximated with piecewise linear segments. Segments are chosen adaptively to respect a maximum reconstruction error.  

2. **Quantization / Symbolization** – Segment slopes and lengths are clustered (e.g., with k-means), and each cluster is mapped to a symbol. This builds a discrete dictionary of patterns.  

3. **Reconstruction** – From the sequence of symbols, an approximate version of the original time series can be reconstructed, enabling lossy compression.  

![ABBA decomposition](/img_compressed/posts/cs-mva/abba_decomposition.png)

The promise is that instead of modeling thousands of raw values, one can train models on much shorter symbolic sequences.

More details on the method can be found in the [report](https://raw.githubusercontent.com/clementw168/abba-lstm/main/report.pdf).

## Experiments

We tested ABBA on two datasets:  

1. **Synthetic sinusoidal signal** (clean, periodic).  
2. **Monthly Sunspots dataset** (real-world, noisy, quasi-periodic).  

### Reconstruction Quality

- On the sinusoidal dataset, ABBA reconstructs the signal almost perfectly.  
- On the Sunspots dataset, more symbols are required to capture variability, and reconstruction is less precise.  

<div style="display: flex; justify-content: center; gap: 20px;">
  <div style="flex: 1; text-align: center;">
    <img src="/img_compressed/posts/cs-mva/abba_example_sinus.png" alt="ABBA reconstruction - sinusoidal" style="max-width:100%; border-radius:10px;">
    <p><em>ABBA reconstruction on a sinusoidal dataset</em></p>
  </div>
  <div style="flex: 1; text-align: center;">
    <img src="/img_compressed/posts/cs-mva/abba_example_sunspot.png" alt="ABBA reconstruction - sunspots" style="max-width:100%; border-radius:10px;">
    <p><em>ABBA reconstruction on the Sunspots dataset</em></p>
  </div>
</div>

While reconstruction is decent, one can already question whether symbol sequences without inherent numerical meaning are suitable inputs for forecasting.  


## Forecasting with LSTM

We compared two forecasting approaches:  

- **Raw LSTM**: trained directly on raw time series values.  
- **ABBA-LSTM**: trained on ABBA-generated symbol sequences.  

![Results on sinusoidal](/img_compressed/posts/cs-mva/sinus_results.png)
![Results on sunspots](/img_compressed/posts/cs-mva/sunspot_results.png)

| Dataset         | Raw LSTM (DTW ↓) | ABBA-LSTM (DTW ↓) |
|-----------------|------------------|-------------------|
| Sinusoidal      | **0.001–0.015**  | 0.034–0.134       |
| Sunspots        | **0.022–0.068**  | 0.319–0.357       |

Across both datasets, **ABBA-LSTM performed significantly worse**. This outcome is unsurprising: ABBA compresses signals into a symbolic dictionary, but those symbols carry no semantic or numerical continuity for forecasting models.  


## Critical Findings

Initially, we were surprised at the discrepancy between our results and those reported in the original papers. After reviewing the [authors’ official implementation](https://github.com/nla-group/ABBA), we discovered:  

- Some methodological inconsistencies between the paper and the code.  
- More importantly, the paper reported results where models were trained **directly on the test set**, inflating performance.  

This was disappointing, especially given the publication venue (*Data Mining and Knowledge Discovery*). It was a valuable lesson in the importance of looking at both code and methodology when reproducing research.


## Documentation

- 📄 [Complete Project Report](https://raw.githubusercontent.com/clementw168/abba-lstm/main/report.pdf)  
- 💻 [GitHub Repository](https://github.com/clementw168/abba-lstm)  


## References

1. **Elsworth, S., & Güttel, S. (2020)**. ABBA: Adaptive Brownian bridge-based symbolic aggregation of time series. *Data Mining and Knowledge Discovery*, 34(4), 1175-1200. [Link](https://arxiv.org/abs/2003.12469)  
2. **Elsworth, S., & Güttel, S. (2020)**. Time series forecasting using LSTM networks: A symbolic approach. *arXiv preprint arXiv:2003.05672*. [Link](https://arxiv.org/abs/2003.05672)  
