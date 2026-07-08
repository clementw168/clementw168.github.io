---
layout:     post
title:      "Delivery Date Estimation Model at Mirakl"
subtitle:   "Building a Time Series Forecasting Model for Marketplace Orders"
date:       2025-10-07 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/mirakl/edd.png"
header-mask: 0.4
catalog: true
published: true
tags:
    - Machine Learning
    - Time Series
    - Development
---


**Mirakl** builds enterprise marketplace software, letting retailers, manufacturers, and B2B companies launch and run their own online marketplaces.


### Joining Mirakl

I joined Mirakl as a **Data Scientist** in **December 2024**, and got put on one of the company's machine learning initiatives: **estimating delivery dates for marketplace orders**.


### Project Overview

The goal was to predict the arrival date of an order, framed as a regression task with interval prediction: not just a point estimate, but a window the customer could trust. I can't go into detail on the data, models, or metrics, but the core of it was statistics and classical machine learning. The project covered the whole lifecycle: data collection and preprocessing, an initial POC, validating that POC with the business team, then pipeline orchestration, production deployment, testing, and monitoring.

The hardest part wasn't the modeling, it was agreeing with the product manager on what "good" actually meant. We started with a target of a 99% on-time rate within a 1-day window. Through the POC, it became clear that target wasn't realistic: some sellers had a lot of variance in how they operated, some working 5 days a week, others 6, and the underlying data was pretty messy. Getting to a metric that reflected reality, instead of the original wishful one, took as much work as the model itself, if not more.


<div class="responsive-iframe-container">
  <iframe src="https://player.vimeo.com/video/1090794835" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
</div>

<style>
.responsive-iframe-container {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 56.25%; /* 16:9 aspect ratio (360/640 * 100) */
  margin: 20px 0;
}

.responsive-iframe-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
  border-radius: 8px;
}

/* Mobile adjustments */
@media (max-width: 768px) {
  .responsive-iframe-container {
    padding-bottom: 60%; /* Slightly taller on mobile for better viewing */
  }
}
</style>


### From Beta to General Release

The **beta program** launched in **July 2025** with three pilot clients, providing estimated delivery dates for over **50,000 orders per week**.  
After several months of testing and monitoring, we released the feature to **general availability** in **October 2025**.

<div class="responsive-iframe-container">
  <iframe src="https://drive.google.com/file/d/1hc2On6gV9T0k-FsP3IJlNvSUWuybGPiL/preview" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>
</div>

<style>
.responsive-iframe-container {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 56.25%; /* 16:9 aspect ratio (480/640 * 100) */
  margin: 20px 0;
}

.responsive-iframe-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: none;
  border-radius: 8px;
}

/* Mobile adjustments */
@media (max-width: 768px) {
  .responsive-iframe-container {
    padding-bottom: 60%; /* Slightly taller on mobile for better viewing */
  }
}
</style>





### What I Learned

I worked closely with SREs, data engineers, product managers, developers, and BI analysts, and everything was managed as code with **Spark**, **Databricks**, **Airflow**, and **MLflow**. But the main thing I took away wasn't technical. Data science is mostly about understanding the client's actual problem, discussing what really matters to them, and convincing them your solution will help even if it's not perfect.


### Final Thoughts

I really liked this project. It taught me what it means to bring a model into production and deal with reliability, scale, and real-world constraints.

That said, working through it also made me realize something about myself. While I enjoyed the engineering and operational side, my real interest is in research. That's what led me back toward research-oriented projects after the algorithm shipped.

