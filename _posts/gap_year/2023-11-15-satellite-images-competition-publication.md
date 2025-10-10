---
layout:     post
title:      "Satellite Images Competition and Publication at BiDS 2023"
subtitle:   "Predicting Leaf Area Index from Sentinel Satellite Data"
date:       2023-11-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/gap_year/satellite.png"
catalog: true
published: true
tags:
    - Satellite Imagery
    - Remote Sensing
    - Computer Vision
    - Competition
    - Publication
pride_score: 1
---

## Project Overview

In April 2023, I participated in a 3-week competition to predict the Leaf Area Index (LAI) for each pixel in satellite images from Sentinel-1 and Sentinel-2. The project combined remote sensing, computer vision, and deep learning, and led to a publication at the [Big Data from Space (BiDS) 2023 conference](https://www.bigdatafromspace2023.org/) in Vienna, Austria.

![Data visualization](/img_compressed/posts/gap_year/lai_pred.png)

Our work was accepted at BiDS 2023:

**Wang, C., Debouchage, A., Goldité, V., Wery, A., & Salzinger, J. (2024).** Leveraging Multi-Temporal Sentinel 1 and 2 Satellite Data for Leaf Area Index Estimation With Deep Learning. *arXiv preprint arXiv:2410.19787*. [PDF](https://arxiv.org/pdf/2410.19787)

The paper details how we leveraged multi-temporal Sentinel-1 and Sentinel-2 imagery, combining historical LAI measurements with current satellite data, to improve predictions at 256×256 pixel resolution. For technical details on the models, data processing, and evaluation, please refer directly to the [paper](https://arxiv.org/pdf/2410.19787) and the [GitHub repository](https://github.com/clementw168/LeafNothingBehind).

## Reflections

The paper submission deadline was just one week after the competition ended, so the writing was rushed and we had limited time for ablation studies. It was my first scientific paper. I’m aware there is room for improvement in the analysis, but the experience of turning a competition result into a publication was interesting.
