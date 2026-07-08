---
layout:     post
title:      "Analyzing Business Opportunities at Etandex"
subtitle:   "Commercial Opportunity Prediction as a Freelance Business Intelligence Analyst"
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

Before returning from Germany, I took on a two-month freelance mission as a **Business Intelligence Analyst** at [Etandex](https://www.etandex.fr/), one of France’s largest construction and infrastructure companies. The goal was to predict the likelihood of converting a commercial opportunity into a signed contract and provide actionable insights into the model’s decisions. It was a nice opportunity to try something different from my usual work.

## The data

I got an Excel table of business opportunities filled in manually by employees: where the opportunity came from, which sales consultant worked it, that consultant's age and years of experience, the position of the contact person on the client's side, the type of construction contract, the location, and more. I cleaned it up (duplicates, missing and negative values, inconsistent formats, categorical encoding), then enriched it with employee data from HR and demographic data from INSEE, and labeled each opportunity as won or lost based on its final status.

Running PCA and t-SNE on the result showed no clean separation between winning and losing opportunities, so I knew going in that this wouldn't be an easy classification task.

## Modeling

I tried logistic regression, random forest, XGBoost, and LightGBM on an 80/20 split, weighting recent opportunities more heavily since they were more representative of the current business. XGBoost came out ahead with 69% test accuracy, just above LightGBM and random forest.

## Explainability

This was the part that was genuinely new to me. Before this project I had mostly done deep learning, where you rarely need to explain a single prediction to anyone. Etandex needed the opposite: not just a working model, but a model whose decisions they could actually justify to their sales teams.

I used feature importance to get a first read on which factors mattered most (opportunity amount and consultant characteristics came up a lot, though obviously correlation isn't causation), SHAP values to break down each prediction's drivers globally and locally (having a decision-maker as the contact consistently helped, while consultant seniority cut both ways depending on context), and Anchor rules to turn predictions into simple if-then statements that non-technical stakeholders could actually read.

![Shap](/img_compressed/posts/gap_year/shap.png)

## Wrapping up

I presented the whole thing to Etandex's executive team at the end of the mission, which was pretty impressive for me. Most of my work until then had been research and feasibility projects, far from anyone actually making decisions with what I built. Standing in front of executives and defending my model was a different kind of pressure, and I'm glad I went through it.

