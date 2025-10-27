---
layout:     post
title:      "Lymphocytosis Classification"
subtitle:   "Detection of Tumoral Lymphocytosis from Blood Smears"
date:       2024-03-01 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/cs-mva/lympho.png"
header-mask: 0.4
catalog: true
published: true
tags:
    - Student project
    - Healthcare AI
    - Deep Learning
    - Computer Vision
---

## Project Overview

This project aimed to build a classifier to detect **tumoral lymphocytosis** using blood smear images and patient metadata. The dataset, collected at Lyon Sud University Hospital, included 204 patients (142 for training and 42 for testing). The goal was to support clinicians in identifying cases that require **flow cytometry**, reducing costs and improving diagnostic accuracy.

This work was part of the [Deep Learning for Medical Imaging course](https://www.aramislab.fr/teaching/DLMI-2020-2021/) by Olivier Colliot and Maria Vakalopoulou.


## Approach

We received multiple cell images per patient along with tabular patient information. I experimented with three modeling strategies:

1. **Tabular-only model** using patient metadata.  
2. **CNN-based image model** ignoring tabular data.  
3. **Multi-modal model** combining images and tabular features.

Due to the small dataset, results were very noisy, with metrics fluctuating on both the validation set and the Kaggle leaderboard. I decided to drop the course because I felt like the design of the competition was wrong. Another reason was that I wanted to focus on other projects. My submission placed **top 6 out of 30 participants**, even though I was around 15th on the public leaderboard before the private evaluation was revealed.

The experience highlighted the limitations of small datasets in deep learning for medical imaging and the importance of robust evaluation.

## Code Repository

All code for this project is available on GitHub: [Lymphocytosis Classification](https://github.com/clementw168/Lymphocytosis-classification)
