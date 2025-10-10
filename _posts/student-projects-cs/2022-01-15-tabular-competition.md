---
layout:     post
title:      "Tabular Data Competition: Building Classification from Geodata"
subtitle:   "Ranked 2nd over 72 in Course Competition on Tabular Data"
date:       2022-01-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/student-projects/tabular-competition/full_data_dark.jpg"
catalog: true
published: true
tags:
    - Student project
    - Machine Learning
    - Tabular Data
    - Competition
---


## Project Overview

Ranked **2nd out of 72 participants** in a machine learning course competition focused on tabular data classification. The challenge involved classifying buildings into 5 distinct categories using a combination of geographical data and building metadata.

The competition required participants to leverage both geographical coordinates and building characteristics to accurately predict building types, making it a complex feature engineering and model selection challenge.

![Visualization of geo data](/img_compressed/posts/student-projects/tabular-competition/full_data.jpg)

## Technical Approach

### Feature Engineering

Feature engineering was the key to success in this competition. We created over 400 features by leveraging domain knowledge about urban planning and geographical data. The main feature categories included:

- **Temporal Features**: Extracted day, month, year from dates and computed time gaps between events
- **Categorical Encoding**: Converted urban types and geographical categories into binary attributes  
- **Geometric Features**: Calculated length, width, and their ratios to distinguish between different building types (e.g., roads vs. buildings)
- **Spatial Neighbors**: Exploited the fact that the dataset contained blocks of buildings from satellite views by adding features from the k-nearest neighbors within a certain radius

![Visualization of some classes](/img_compressed/posts/student-projects/tabular-competition/buildings.png)

### Model Selection & Ensemble

We tested multiple models and achieved the best results with an ensemble of three gradient boosting algorithms:

- **XGBoost**: Primary model with extensive hyperparameter tuning
- **LightGBM**: Optimized for speed and memory efficiency
- **CatBoost**: Specialized in handling categorical features

The ensemble was validated using 10-fold cross-validation with manual hyperparameter tuning for each model.

![Models comparison](/img_compressed/posts/student-projects/tabular-competition/model_bench.png)

### Results & Lessons Learned

This was my first experience with classical machine learning, which provided valuable insights into the differences between traditional ML and deep learning approaches.

**Key Takeaways:**
- **Feature Engineering Dominance**: Unlike deep learning where architecture matters most, traditional ML performance heavily depends on feature engineering
- **Ensemble Benefits**: Combining multiple models consistently outperformed individual models
- **Validation Strategy**: Proper cross-validation prevented overfitting and provided reliable performance estimates
- **Domain Knowledge**: Understanding spatial relationships and urban planning concepts was crucial for creating meaningful features

### Full Report
[Complete Project Report](/assets/posts/ml_course_kaggle_report.pdf).

