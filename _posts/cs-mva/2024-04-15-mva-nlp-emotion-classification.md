---
layout:     post
title:      "Aspect-Based Sentiment Analysis"
subtitle:   "Understanding Sentiment with Respect to Specific Aspects"
date:       2024-04-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/cs-mva/aspect.png"
header-mask: 0.5
catalog: true
published: true
tags:
    - Student project
    - Deep Learning
    - Natural Language Processing
    - Aspect-Based Analysis
    - Transformers
---

## Project Overview

As part of the [NLP course at Naver Labs Europe](https://sites.google.com/view/dsba-nlp-course/home?authuser=0), we tackled **aspect-based sentiment analysis**.  
The task is to classify a sentence’s sentiment (**positive / negative / neutral**) **with respect to a specific aspect-term** (e.g., *food quality*, *service*, *ambiance*).

This makes the task more challenging than standard sentiment analysis, since the same sentence may contain multiple aspects with different polarities.


## Task Visualization

![Emotion classification](https://raw.githubusercontent.com/clementw168/nlp-aspect-term-polarity/main/images/sample.png)


## Model Architecture

We fine-tuned **DistilBERT**, a lightweight version of BERT, and adapted it to our task:  

- **Input Encoding:** We used `[SEP]` tokens to separate the *aspect*, *sub-theme*, and the *sentence*.  
- **Aspect Markers:** Two custom tokens `[START_WORD]` and `[END_WORD]` were added around the aspect-term, helping the model focus on the relevant part of the text.  
- **Categorical Features:** Aspect categories and subcategories were one-hot encoded, then concatenated with DistilBERT’s pooled output through a small **MLP classifier**.  

This design allowed the model to leverage both contextual embeddings and structured aspect information.  

![Architecture](https://raw.githubusercontent.com/clementw168/nlp-aspect-term-polarity/main/images/model.png)


## Data Augmentation

The dataset was small (~1500 training samples), so we applied **aspect replacement augmentation**:  
- Replace an aspect-term with another term from the same category.  
- This increased data diversity, though some generated sentences were nonsensical.  


## Results

We trained on **1503 samples** and tested on **376 samples**.  


| Metric | Train set | Test set |
|:---: | :---: | :---: |
| Accuracy | 0.95 | 0.80 |
| F1 Score | 0.93 | 0.79 |




The model learned well but was prone to **overfitting** due to the dataset’s limited size. Dropout layers helped slightly, but adding complexity to the MLP often worsened results.  


## Code Repository

📂 [GitHub Repository](https://github.com/antoine311200/nlp-aspect-term-polarity)  


## References

- Sanh, Victor, et al. *DistilBERT: a distilled version of BERT.* arXiv:1910.01108 (2019).  
- Qiu, Xipeng, et al. *Pre-trained models for NLP: A survey.* (2020). [[pdf]](https://arxiv.org/pdf/2003.08271)  
- Acheampong, Adoma, et al. *Comparative analyses of BERT, RoBERTa, DistilBERT, and XLNet for emotion recognition.* (2020). [[pdf]](https://arxiv.org/ftp/arxiv/papers/2104/2104.02041.pdf)  

