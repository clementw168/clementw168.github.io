---
layout:     post
title:      "Being a Machine Learning Consultant at Paris Digital Lab"
subtitle:   "Various Computer Vision projects for companies"
date:       2022-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/banners/paris_digital_lab.jpg"
header-mask: 0.3
catalog: true
published: true
tags:
    - Gap year
    - Internship
    - Consulting
    - Computer Vision
    - Deep Learning
    - Object Detection
    - Transformers
---



## Experience Overview

After a year and a half of general engineering studies, I wanted to step into the professional world before finishing my degree. That’s when I started my gap year and joined the Paris Digital Lab. During my time at Paris Digital Lab, I worked on **three Data science projects**, each lasting 7 weeks. Every project followed a sprint-like rhythm, with the goal of delivering a functional MVP to the client. This meant quick decision-making, rapid prototyping, and iterative development.

Each project had its own challenges and learning curves. Some involved exploring cutting-edge research, while others were more engineering-focused, requiring practical solutions with tight deadlines. I quickly learned how to break down complex problems, experiment with multiple approaches, and communicate results clearly to both technical and non-technical stakeholders.

The experience taught me a lot about working in a small team under pressure. We had to balance research, coding, debugging, and preparing presentations, often all at the same time. It pushed me to be both rigorous and creative, and gave me a firsthand view of how innovation happens in a fast-moving environment. It was the first time I faced clients and had to deliver results that were actually useful to them.


## About Paris Digital Lab

Paris Digital Lab runs a unique program called the **Digital Tech Year**, a one-year gap-year experience for students. The first six months focus on real-world tech projects, where small teams of 3–4 students work full-time on company challenges in 7-week sprints. The goal of each sprint is to deliver a **Minimum Viable Product (MVP)**, allowing companies to test ideas quickly. The second half of the program is an internship in a tech hub, offering a more in-depth experience in a startup or innovation-driven environment.



## Project 1: Confidential Company – YOLOv3 on Radio Wave Detection

This project was unusual. The client needed to detect and classify radio signals in the IQ format, basically a time series of complex numbers representing two orthogonal components of a radio signal. Our first reaction was to visualize the Fast Fourier Transform of the signal, and it was immediately obvious that treating this like an object detection problem could work surprisingly well.

We turned the time-frequency representation into an image-like format and applied YOLOv3 for detection. The intuition was simple: each type of radio signal manifests as a distinct pattern in the spectrogram, much like an object in a picture. I worked on YOLOv3 and it achieved **0.95 mAP @ IOU 0.5**, which was largely beyond what the client expected. The other two members worked on RCNN and Unet. I had the best results with YOLOv3.

![Radio Wave Detection](/img_compressed/posts/gap_year/radio_wave_detection.png)

It was fascinating to see how techniques from computer vision could transfer to signal processing problems. It also taught me the importance of representation: a slightly different visualization could completely change the effectiveness of a model. Most of my time was spent on understanding the literature of Object Detection and modifying a Github repository to fit our needs.

**Tech stack:** PyTorch, YOLOv3, RCNN, Unet, signal processing.


## Project 2: L’Oréal Research & Innovation – Retrieving Lipstick from Selfies

This project was much simpler. L’Oréal wanted to identify the lipstick a person was wearing from a selfie. The pipeline was straightforward in theory: detect the lips with Face Landmarks Detection, crop them, predict the optical properties of the lipstick, and find the best match in a lipstick database.

In practice, there were a few twists. First, I used Dlib for face landmarks detection, which reliably localized lips. Then, I trained a regression CNN to predict color properties in LAB space — perceptually uniform, which makes matching more accurate. The client also wanted uncertainty estimation for each prediction, so I implemented **Deep Evidential Regression**, which gave not only a color prediction but also a confidence interval. By the end of the project, we had a fully functioning MVP capable of suggesting lipstick matches from a single selfie with reasonable confidence.

![Lipstick from Selfies](/img_compressed/posts/gap_year/lipstick_retrieval.png)

[Amini, Alexander, et al. "Deep evidential regression." Advances in neural information processing systems 33 (2020): 14927-14937.](https://proceedings.neurips.cc/paper_files/paper/2020/file/aab085461de182608ee9f607f3f7d18f-Paper.pdf)

**Tech stack:** TensorFlow, CNN regression, Dlib, Deep Evidential Regression, LAB color space.


## Project 3: Oorion – Personalized Object Detection with CLIP

The final project was a bit more research-oriented. Oorion wanted a system where users could personalize detected objects and add new classes to YOLOv5 with minimal manual annotation. 

This was at the peak of zero-shot and few-shot learning hype. CLIP was just released and changed the game. I spent the first few weeks diving into literature: few-shot image classification, few-shot object detection, class-agnostic detection, open-world object detection, CLIP, and referring expression comprehension. Eventually, I designed a solution combining a class-agnostic detector with CLIP embeddings on top. The idea was simple but elegant: the detector finds all objects, and CLIP matches them to the desired class without retraining for each new label.

![Personalized Object Detection](/img_compressed/posts/gap_year/oorion.png)

We achieved **0.20 mAP on COCO**, which wasn’t groundbreaking, but the experience was interesting. We achieved interesting results with personalization since CLIP image-to-image distance is very good to retrieve personalized objects.

**Tech stack:** PyTorch, Hugging Face, CLIP, few-shot and zero-shot object detection, class-agnostic detection.


## Reflections

These three projects were very different, but together they gave me a broad perspective on applied machine learning in a consulting context:

- **Adaptability is key:** You need to quickly understand the problem and constraints. There’s no time to overthink and you need to be able to learn quickly.
- **Representation matters:** Choosing the right pipeline and input format (spectrogram, cropped lips, embeddings) is often more important than the model itself.
- **Balance theory and practicality:** Some solutions are elegant on paper but hard to deploy; others are hacky but work reliably for the client.
- **Continuous learning:** In a consulting environment, you encounter new domains every few weeks, which forces rapid acquisition of knowledge.

I left Paris Digital Lab with a stronger sense of practical ML, faster prototyping skills, and a renewed excitement for building systems that actually solve real-world problems. Consulting wasn’t my long-term path, but it was an incredible training ground that taught me lessons I carry into every project today.

---

For more about Paris Digital Lab: [https://paris-digital-lab.com/](https://paris-digital-lab.com/)
