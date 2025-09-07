---
layout:     post
title:      "Diagnostic Assistance with AI at Polygon Technologies"
subtitle:   "Video Analysis for Learning Differences Diagnosis using Time Series Classification"
date:       2023-01-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Medical AI
    - Video Analysis
    - Time Series Classification
    - Diagnostic Assistance
    - AWS
    - Computer Vision
    - Healthcare
---

> "Six-month internship at Polygon Technologies working on AI-assisted diagnosis of learning differences through video analysis and time series classification."

![Polygon banner](/img/pages/polygon-banner.png)

## About Polygon Technologies

Six-month internship at Polygon. [Polygon](https://hellopolygon.com/) is a new kind of psychology practice that provides remote diagnostics for dyslexia, ADHD, and other learning differences. The company is based in Santa Monica, California, United States.

## Project Overview

I worked on a project to assist diagnosis of learning differences. The global idea is that we record testing sessions of patients with a camera. From these videos, we extract all the useful information as time series. And then, we use these time series to understand what happened at what moment because of what. This approach gets rid of high-dimensional video data. At the same time, it makes the global pipeline much more interpretable which is so important in the medical field where mistakes can cost a lot.

## Technical Approach

### Video Analysis Pipeline
- **Video Recording**: Capturing patient testing sessions with cameras
- **Feature Extraction**: Converting high-dimensional video data to meaningful time series
- **Time Series Analysis**: Analyzing temporal patterns in patient behavior
- **Interpretable AI**: Creating explainable diagnostic assistance systems

### Key Features Developed

#### 1. Data Unification on AWS Storage
- **Centralized Storage**: Unifying all patient data on AWS infrastructure
- **Data Organization**: Structured storage for video and extracted features
- **Access Control**: Secure access to sensitive medical data
- **Scalability**: Handling growing datasets efficiently

#### 2. Data Cleaning and Standardization
- **Quality Control**: Ensuring data quality and consistency
- **Standardization**: Creating uniform data formats across different sources
- **Validation**: Implementing data validation and error checking
- **Preprocessing**: Preparing data for analysis and modeling

#### 3. Voice Activity Detection with Gaussian Mixture Models
- **Audio Processing**: Analyzing speech patterns in patient sessions
- **GMM Implementation**: Using Gaussian Mixture Models for voice detection
- **Temporal Analysis**: Understanding speech timing and patterns
- **Feature Extraction**: Converting audio to meaningful time series features

#### 4. 3D Face Landmarks Detection with Face Alignment Networks
- **Facial Analysis**: Detecting and tracking facial landmarks in 3D
- **Behavioral Indicators**: Using facial expressions as diagnostic indicators
- **Temporal Tracking**: Monitoring facial changes over time
- **Feature Engineering**: Creating meaningful behavioral time series

#### 5. Speech-to-Text Solutions Benchmarking
- **Technology Evaluation**: Comparing Whisper, AWS Transcribe, and other solutions
- **Performance Analysis**: Evaluating accuracy and reliability
- **Cost Optimization**: Balancing performance with cost considerations
- **Integration**: Implementing best-performing solutions

#### 6. AWS Batch Pipelines for Cost Optimization
- **Batch Processing**: Optimizing feature extraction costs
- **Resource Management**: Efficient use of cloud computing resources
- **Scalability**: Handling varying workloads efficiently
- **Cost Control**: Monitoring and optimizing processing costs

#### 7. Time Series Visualization with Plotly and Streamlit
- **Interactive Dashboards**: Creating user-friendly visualization interfaces
- **Temporal Visualization**: Displaying time series data effectively
- **Real-Time Updates**: Providing live updates during analysis
- **User Interface**: Making complex data accessible to clinicians

#### 8. Time Series Classification and Breakpoint Detection
- **Pattern Recognition**: Identifying diagnostic patterns in time series
- **Breakpoint Detection**: Detecting significant changes in patient behavior
- **Classification**: Categorizing different types of behavioral patterns
- **Diagnostic Support**: Providing AI assistance for clinical diagnosis

## Technical Stack

- **AWS**: Cloud infrastructure and services
- **Docker**: Containerization for consistent deployments
- **PyTorch**: Deep learning framework for model development
- **Streamlit**: Web application framework for dashboards
- **Plotly**: Interactive visualization library
- **Computer Vision**: Advanced image and video processing
- **Time Series Analysis**: Specialized techniques for temporal data

## Medical Applications

### Diagnostic Support
- **Learning Differences**: Assisting in diagnosis of dyslexia, ADHD, and other conditions
- **Behavioral Analysis**: Understanding patient behavior patterns
- **Objective Assessment**: Providing quantitative measures for diagnosis
- **Clinical Decision Support**: Supporting clinicians with AI insights

### Interpretability and Trust
- **Explainable AI**: Making AI decisions transparent and understandable
- **Clinical Validation**: Ensuring AI recommendations align with clinical knowledge
- **Error Analysis**: Understanding and preventing diagnostic errors
- **Trust Building**: Building confidence in AI-assisted diagnosis

## Technical Innovation

### Video-to-Time-Series Conversion
- **Dimensionality Reduction**: Converting high-dimensional video to manageable time series
- **Feature Engineering**: Creating meaningful behavioral indicators
- **Temporal Modeling**: Understanding temporal patterns in patient behavior
- **Interpretability**: Making complex video data interpretable for clinicians

### Multi-Modal Analysis
- **Audio-Visual Fusion**: Combining speech and visual information
- **Behavioral Indicators**: Using multiple modalities for comprehensive analysis
- **Temporal Synchronization**: Aligning different data streams in time
- **Comprehensive Assessment**: Providing holistic view of patient behavior

## Learning Outcomes

### Technical Skills
- Advanced video analysis and computer vision
- Time series analysis and classification
- AWS cloud infrastructure and services
- Medical AI and diagnostic assistance systems

### Domain Knowledge
- Learning differences and diagnostic criteria
- Medical AI applications and requirements
- Healthcare data privacy and security
- Clinical workflow integration

### Professional Experience
- Working in healthcare technology startup
- International collaboration and remote work
- Medical device development processes
- Regulatory and compliance considerations

## Impact and Applications

### Healthcare Innovation
- **Remote Diagnostics**: Enabling remote assessment of learning differences
- **Objective Measurement**: Providing quantitative diagnostic measures
- **Accessibility**: Making diagnostic services more accessible
- **Efficiency**: Streamlining diagnostic processes

### Clinical Benefits
- **Improved Accuracy**: Supporting clinicians with AI insights
- **Time Efficiency**: Reducing time required for comprehensive assessment
- **Consistency**: Providing standardized assessment methods
- **Documentation**: Creating detailed records of patient sessions

## Future Directions

- Integration with electronic health records
- Extension to other diagnostic applications
- Real-time diagnostic assistance
- Mobile application development

## Tags

- **Medical AI**: Artificial intelligence in healthcare applications
- **Video Analysis**: Computer vision for video understanding
- **Time Series Classification**: Machine learning for temporal data
- **Diagnostic Assistance**: AI support for medical diagnosis
- **AWS**: Amazon Web Services cloud infrastructure
- **Computer Vision**: AI for visual understanding
- **Healthcare**: Medical technology and applications
