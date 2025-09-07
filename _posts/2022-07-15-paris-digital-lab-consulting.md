---
layout:     post
title:      "Machine Learning Consultant at Paris Digital Lab"
subtitle:   "Various Computer Vision Projects for Companies - 3 Projects of 7 Weeks Each"
date:       2022-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Consulting
    - Computer Vision
    - Machine Learning
    - YOLO
    - Object Detection
    - Deep Learning
    - MVP
---

> "Three projects of 7 weeks each with different companies, each with a Minimal Viable Product at the end following Scrum methodology."

![PDL banner](/img/pages/paris_digital_lab.jpg)

## About Paris Digital Lab

After one and half years of studying general engineering, I wanted to discover the professional world so I started my one-and-half-year gap year. My first internship was with the Paris Digital Lab, a tech consulting company as a Machine learning consultant.

## Experience Overview

I did 3 projects of 7 weeks with different companies, each of them with a Minimal viable product at the end following Scrum methodology. Consulting was not my thing. Even though projects can be very different and challenging, most of the time, they were theoretically too simple and I had no right to choose what to work on.

## Project 1: Confidential Company - YoloV3 on Radio Wave Detection

### Project Overview
This project was about detecting and classifying radio signals in the IQ format. The IQ format is a time series of complex numbers, representing two orthogonal components of a radio signal.

### Technical Approach
A visualization of the Fast Fourier Transform of the signal was enough to convince us that Object detection was a good way to solve that problem.

### Results
YOLOv3 achieved **0.95 mAP @ IOU 0.5** on the task.

### Technical Stack
- **PyTorch**: Deep learning framework
- **YOLO**: Object detection architecture
- **RCNN**: Alternative object detection approach
- **Object Detection**: Core computer vision task
- **UNet**: Semantic segmentation architecture
- **Semantic Segmentation**: Pixel-level classification
- **Signal Processing**: Radio signal analysis

## Project 2: L'Oréal Research & Innovation - Retrieving Lipstick from Selfies

### Project Overview
This project is about lipstick retrieval from a selfie. The approach is to first, find the lips with Face landmarks detection, then crop on these lips and predict the optical properties of the lipstick. From these properties, find the best fit in a database of lipsticks.

### Technical Implementation
- **Face Landmarks Detection**: Used Dlib out-of-the-box for face landmarks detection
- **Regression CNN**: The regression task was made with a regression CNN
- **Matching Algorithm**: The matching was a weighted L2 score on optical properties
- **GAN Data Generation**: The available data was generated with a GAN
- **Color Space Conversion**: For the colors, moved into the LAB space to have a perceptual distance
- **Uncertainty Estimation**: Implemented [Deep evidential regression](https://arxiv.org/abs/1910.02600) for uncertainty estimation

### Technical Stack
- **TensorFlow**: Deep learning framework
- **Deep Regression**: Advanced regression techniques
- **Uncertainty Estimation**: Quantifying prediction confidence
- **Dlib**: Computer vision library for face detection

## Project 3: Oorion - Personalized Object Detection with CLIP

### Project Overview
This project was an exploration of everything that can be done to personalize detected objects and add classes to YOLOv5 with the minimum amount of manual annotation.

### Research and Implementation
I did a huge literature review of:
- **Few-shot Image Classification**: Learning from limited examples
- **Few-shot Object Detection**: Object detection with minimal data
- **Class Agnostic Detection**: Detecting objects without predefined classes
- **Open-world Object Detection**: Detecting objects from unknown classes
- **CLIP**: Contrastive Language-Image Pre-training
- **Referring Expression Comprehension**: Understanding natural language references

### Technical Solution
I designed a solution with a class-agnostic detector and CLIP on top of it. It achieved **0.20 mAP on COCO**. However, a few days before the end of my internship, [One for all](https://arxiv.org/abs/2202.03052) was released, and could do the same better and faster.

### Technical Stack
- **PyTorch**: Deep learning framework
- **Hugging Face**: Model hosting and distribution
- **Few-shot Learning**: Learning from limited examples
- **CLIP**: Vision-language model
- **Zero-shot Learning**: Learning without training examples

## Learning Outcomes

### Technical Skills
- **Computer Vision**: Advanced image processing and analysis
- **Object Detection**: YOLO and other detection architectures
- **Deep Learning**: Various neural network architectures
- **Signal Processing**: Radio signal analysis and processing
- **Face Recognition**: Facial landmark detection and analysis
- **Few-shot Learning**: Learning from limited data

### Professional Experience
- **Consulting Environment**: Working in client-facing consulting role
- **Project Management**: Managing multiple concurrent projects
- **Scrum Methodology**: Agile development practices
- **MVP Development**: Creating minimal viable products
- **Client Communication**: Working with diverse client requirements

### Industry Insights
- **Theoretical vs Practical**: Understanding the gap between academic and industry needs
- **Project Constraints**: Working within client requirements and limitations
- **Time Management**: Delivering results within tight deadlines
- **Technology Selection**: Choosing appropriate technologies for specific problems

## Challenges and Reflections

### Consulting Limitations
- **Limited Choice**: No control over project selection or direction
- **Theoretical Simplicity**: Projects often lacked theoretical complexity
- **Client Constraints**: Working within strict client requirements
- **Time Pressure**: Delivering results within fixed timelines

### Technical Challenges
- **Domain Adaptation**: Adapting to different industry domains
- **Data Quality**: Working with varying data quality across projects
- **Performance Requirements**: Meeting specific accuracy and speed requirements
- **Integration**: Integrating solutions into existing client systems

## Impact and Applications

### Client Value
- **Practical Solutions**: Delivering working solutions for real business problems
- **Technical Expertise**: Providing machine learning expertise to clients
- **Innovation**: Introducing new technologies and approaches
- **Knowledge Transfer**: Educating clients about AI capabilities

### Personal Development
- **Industry Exposure**: Understanding different industry applications
- **Problem Solving**: Developing skills in diverse problem domains
- **Communication**: Learning to communicate technical concepts to non-technical stakeholders
- **Adaptability**: Working across different technical domains

## Future Directions

- Focus on more theoretically challenging projects
- Pursue research-oriented roles
- Develop expertise in specific domains
- Build more control over project selection

## Tags

- **Consulting**: Professional services and client work
- **Computer Vision**: AI for visual understanding
- **Machine Learning**: Artificial intelligence and data science
- **YOLO**: You Only Look Once object detection
- **Object Detection**: Identifying and locating objects in images
- **Deep Learning**: Neural networks and advanced AI
- **MVP**: Minimal Viable Product development
