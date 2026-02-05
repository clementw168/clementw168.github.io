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


**Mirakl** is a French unicorn and global leader in **enterprise marketplace solutions**. Its technology enables leading retailers, manufacturers, and B2B companies to launch and scale online marketplaces efficiently. Mirakl powers hundreds of marketplaces worldwide, helping organizations expand product offerings, improve logistics, and create seamless e-commerce experiences.


### Joining Mirakl

I joined Mirakl as a **Data Scientist** in **December 2024**, where I had the opportunity to work on one of the company’s key machine learning initiatives: **estimating delivery dates for marketplace orders**.  
This project allowed me to apply everything I had learned so far, from model design to full-scale production deployment.


### Project Overview

The goal was to build a **delivery date estimation model** capable of predicting when each order would reach the customer.  
The project covered the **entire machine learning lifecycle**, including:

- Data collection and preprocessing
- Time series model design and proof of concept
- Validation of POC with the business team
- Pipeline orchestration, production deployment, testing
- Performance monitoring


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

Working on this project was both technically challenging and deeply rewarding.  
Here are some of my key takeaways:

- **Cross-functional collaboration** — I worked closely with SREs, data engineers, product managers, developers, and BI analysts.  
- **Modern data infrastructure** — Everything was managed *as code*, leveraging tools like **Spark**, **Databricks**, **Airflow**, and **MLflow**.  
- **End-to-end ownership** — From the first notebook to production pipelines and monitoring dashboards.


### Final Thoughts

This project was an amazing experience in **building a production-grade machine learning system from scratch**. I learned what it truly means to bring a model into production: handling reliability, scalability, and real-world constraints. I am deeply grateful to have had the opportunity to work on this project.

That said, completing this project also helped me realize something deeper about myself. While I enjoyed the engineering and operational aspects, my real passion lies in **research**: exploring new methods, pushing boundaries, and solving major scientific problems.
This realization led me to transition back toward research-oriented projects after the algorithm was released.

