---
layout:     post
title:      "My First Deep Learning Project: Cat Generator"
subtitle:   "From DCGAN to Progressive GAN for cat image generation"
date:       2020-10-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/automatants/gan.png"
catalog: true
published: true
tags:
    - Student organization
    - Automatants
    - Deep Learning
    - Computer Vision
    - Image Generation
    - GAN
---


## Project Overview

This project marked my introduction to deep learning. As my very first deep learning project, I chose to explore the world of Generative Adversarial Networks (GANs) by training models to generate realistic cat images. I was accompanied by a more experienced member of Automatants, the AI student association of CentraleSupélec. The project had a simple goal: train a model to generate images of cats.


![Generated cats](/img_compressed/posts/automatants/gan.png)

## Technical Approach

### 1. Deep Convolutional GAN (DCGAN)
I began with a Deep Convolutional Generative Adversarial Network (DCGAN). I simply took a tutorial on GANs from TensorFlow. This relatively simple model used convolutional layers in both the generator and discriminator, providing a working starting point for image generation.

### 2. Enhanced Architecture with Residual Connections
To improve model performance, I experimented with adding residual connections to the GAN architecture. I had in mind that larger and deeper networks would be able to generate better images.

![Residual Connections](/img_compressed/posts/automatants/residual_gan.png)

### 3. Progressive Growing GAN
Then, I wanted to dive into more complexity. Since StyleGAN seemed a bit too complex, I decided to implement a Progressive GAN. The idea is to start training on very small images (4×4 pixels) and gradually increase the resolution during training. The progressive nature allows the model to learn coarse features first, then refine them to finer details. It is also said to produce more stable training and higher quality results. In practice, the implementation worked but I did not see any significant gain in quality.

![Progressive Growing GAN](/img_compressed/posts/automatants/progressive_gan.png)

## Implementation and Deployment

### Dataset and Preprocessing
The project used a curated dataset of cat images sourced from the internet. The images underwent standard preprocessing steps including resizing, normalization, and augmentation to ensure consistent input for the neural networks.


### Public Deployment
To share the project with a broader audience, I deployed the trained models using TensorFlow.js, enabling real-time cat generation directly in web browsers.

**Try the live demo**: [Cat Generator](https://automatants.cs-campus.fr/projects/cat-generator)

## Reflection and thoughts

I was extremely excited when I was able to generate cat images. I loved the idea of being able to produce something by myself. I learned a lot about programming and deep learning. And even more importantly, I started to learn from blogs, papers, Github repositories, etc. Looking back, I should have done so many things differently. Even though I did all I could at that time, the results are not that good and I am not even sure if my models converged properly. But still, it was a great learning experience.