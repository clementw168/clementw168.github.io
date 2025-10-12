---
layout:     post
title:      "Analyzing Business Opportunities at Etandex"
subtitle:   "Freelance Business Intelligence Analysis with Explainable AI for Commercial Opportunity Prediction"
date:       2023-08-15 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/gap_year/etandex.png"
header-mask: 0.4
catalog: true
published: true
tags:
    - Gap year
    - Consulting
    - Business Intelligence
    - Explainable AI
    - Machine Learning
    - Freelance
---

## Project Overview

Before returning from Germany, I took on a two-month freelance mission as a Business Intelligence Analyst at [Etandex](https://www.etandex.fr/), one of France’s largest construction and infrastructure companies. The goal was to predict the likelihood of converting a commercial opportunity into a signed contract and provide actionable insights into the model’s decisions.

## Data and Methodology

The analysis relied on historical opportunity data from Salesforce, enriched with staff information and INSEE demographic data. Key steps included:

- **Data cleaning**: Removing duplicates, handling missing or negative values, converting formats, and encoding categorical variables.
- **Data enrichment**: Linking opportunities with employee data (age, seniority, role) and geographic data (commune, department).  
- **Labeling outcomes**: Opportunities marked as “won” or “archived won” were positive; “lost” or “archived lost” were negative. Older unresolved opportunities were considered lost.

Visualizations using PCA and t-SNE confirmed the complexity of the classification task, showing no clear separation between success and failure classes.

## Modeling

The dataset was split 80/20 for training and testing. Several models were evaluated for tabular prediction:  

- Logistic Regression  
- Random Forest  
- XGBoost  
- LightGBM  

Recent opportunities were weighted more heavily to reflect their relevance. XGBoost achieved the highest test accuracy at **69%**, slightly outperforming LightGBM and Random Forest.  

## Explainable AI

To interpret the predictions, I applied:  

- **Feature Importance**: Highlighted key factors like opportunity amount and employee characteristics, though correlation does not imply causation.  
- **SHAP values**: Quantified the contribution of each feature to predictions globally and locally. For example, “decision-maker role” consistently had a positive impact, while employee seniority varied depending on context.  
- **Anchor rules**: Provided simple conditional rules explaining why a prediction was made, enhancing interpretability for non-technical stakeholders.  

![Shap](/img_compressed/posts/gap_year/shap.png)

## Takeaways

The project demonstrated how machine learning and explainable AI can help with commercial decision-making by:  

- Optimizing resource allocation toward high-potential opportunities  
- Providing interpretable insights to guide sales strategy

