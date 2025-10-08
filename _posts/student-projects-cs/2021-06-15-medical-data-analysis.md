---
layout:     post
title:      "Infering Genes Links with Unsupervised Methods"
subtitle:   "Collaboration with Pasteur Institute on Gene Expression Analysis"
date:       2021-06-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/student-projects/pasteur.png"
catalog: true
published: true
tags:
    - Medical
    - Unsupervised Learning
    - Gene Expression
    - R Studio
    - PCA
    - Pasteur Institute
---


## Project Overview

This one-week project was conducted in collaboration with the Pasteur Institute, focusing on inferring gene relationships from expression data using unsupervised learning methods in R.

![Logo of Pasteur institut](/img_compressed/posts/student-projects/pasteur_logo.jpg)

Our team consisted of 6 students working with a comprehensive dataset containing gene expression data from 2,000 patients across 5 different stimuli. The objective was to identify meaningful gene interactions and relationships from this dataset.

## Technical Approach

We imported and processed the data using R Studio, which presented its own set of challenges. As this was my first experience with R.

For the core analysis, we focused on two main unsupervised learning techniques:
- **Correlation analysis** to identify linear relationships between gene expressions
- **Joint Graphical Lasso** for sparse precision matrix estimation and network inference


