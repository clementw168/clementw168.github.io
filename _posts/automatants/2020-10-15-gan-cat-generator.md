---
layout:     post
title:      "GAN: Cat Generator - My First Deep Learning Project"
subtitle:   "From DCGAN to Progressive GAN for Cat Image Generation"
date:       2020-10-15 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/automatants/gan.png"
catalog: true
published: true
tags:
    - GAN
    - Deep Learning
    - Image Generation
    - TensorFlow
---

> "My very first Deep learning personal project: generating cat images using various GAN architectures from DCGAN to Progressive GAN."

## Project Overview

This was my very first Deep learning personal project. The goal was to generate cat images. I got a dataset from the internet and took my very first step in Deep learning.

## Generated Results

![Generated cats](/img/posts/automatants/gan.png)

## Technical Evolution

I started with a Deep Convolution Generative Adversarial Network (DCGAN). It was a simple GAN architecture with a few convolutional layers. Then, I wanted to increase the complexity of the model, so I tried a GAN with residual connections. There was a very interesting idea: Progressive GAN. The idea was to train on small 4x4 images, then progressively increase the resolution of the images to reach the target size. 


## Public Deployment

To make it public, I served it on the website of my association with TensorFlow JS. Try it [here](https://automatants.cs-campus.fr/projects/cat-generator).


## Thoughts

Honestly, I was extremely excited when I was able to generate cat images. I had a lot of fun with this project. I learned a lot about GANs and Deep learning. And even more importantly, I started to learn from blogs, papers, Github repositories, etc. Now (in 2023), I should have done so many things differently. The results are not very good and I do not even know if my models converged properly.