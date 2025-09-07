---
layout:     post
title:      "Photogen AI - Founding a Startup on Diffusion Models"
subtitle:   "From Research to Production: AI-Generated Images for Customers"
date:       2023-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img/pages/home-bg.jpg"
catalog: true
published: true
tags:
    - Startup
    - Diffusion Models
    - Generative AI
    - DreamBooth
    - Stable Diffusion
    - Production
    - AWS
---

> "Founding Photogen AI to sell AI-generated images of customers, from research to production deployment on AWS infrastructure."

![Photogen banner](assets/banners/photogen.jpg)

## App Trailer

[![Watch the video](http://img.youtube.com/vi/JS4UvhSgFzs/0.jpg)](https://youtu.be/JS4UvhSgFzs?si=a9LCaDQD6BRvJYIZ)

## Startup Journey

### Inspiration
I got inspired by my internship in a startup in the United States. At the same time, I got really interested in Generative AI. A friend of mine invited me to create Photogen AI. The idea was to sell AI-generated images of customers.

### Vision
- **Personalized AI Art**: Creating custom AI-generated images for individual customers
- **Accessible Technology**: Making advanced AI accessible to everyday users
- **Business Model**: Monetizing cutting-edge generative AI technology
- **User Experience**: Providing seamless image generation service

## Technical Achievements

### DreamBooth Adaptation for Realistic Images
DreamBooth: Fine Tuning Text-to-Image Diffusion Models for Subject-Driven Generation (CVPR 2023) was published and a lot of AI avatar apps popped out of nowhere. However, no one could generate qualitative realistic images. We focused on that, and after a few tricks with DreamBooth, we got decent to really good results.

#### Sample Results
In front of the Eiffel Tower| In front of the Kremlin | In Rome | Professional picture
:-----:|:-----:|:-----: | :-----:
![In front of the Eiffel Tower](assets/images/in%20front%20of%20the%20eiffel%20tower.jpg)| ![In front of the Kremlin](assets/images/in%20front%20of%20the%20Kremlin.jpg)| ![In Rome](assets/images/in%20Rome.jpg)| ![Professional Picture](assets/images/professional%20picture.jpg)|

### Technical Stack
- **Automatic 1111**: Web interface for Stable Diffusion
- **Hugging Face**: Model hosting and distribution
- **Diffusers**: Hugging Face's diffusion model library
- **DreamBooth**: Fine-tuning technique for subject-driven generation
- **Stable Diffusion**: Base diffusion model for image generation

## Production Infrastructure

### AWS Implementation and Cost Optimization
Turning all tests on Google Colab to production on AWS. Creating dashboards and alerts to monitor errors.

#### AWS Dashboard
![AWS Dashboard](assets/images/aws.png)

### Production Pipelines
Two production pipelines on AWS:

#### 1. Inference Pipeline
- **Dynamic Autoscaling**: Automatic scaling based on demand
- **Warmup Strategy**: Pre-warming instances for faster response
- **SQS Monitoring**: Scaling based on message queue length
- **Cost Optimization**: Efficient resource utilization

#### 2. DreamBooth Fine-tuning Pipeline
- **AWS Batch**: Scalable batch processing for model training
- **Resource Management**: Optimized compute allocation
- **Job Scheduling**: Efficient training job orchestration
- **Cost Control**: Monitoring and optimizing training costs

### Technical Stack
- **AWS**: Cloud infrastructure and services
- **Docker**: Containerization for consistent deployments
- **Fast API**: High-performance API framework
- **SQS**: Message queuing for scalable processing
- **CloudWatch**: Monitoring and alerting

## Research and Development

### Paris Gen AI Hackathon
One weekend competition on any technical subject related to Generative AI.

I worked on how to decrease the number of required images for DreamBooth. It became a huge literature review and testing of the latest repositories on:
- **Pose Transfer**: Transferring poses between images
- **Instruct Pix2Pix**: Instruction-based image editing
- **Picture Light Adaptation**: Adjusting lighting in images
- **Background Matting**: Separating subjects from backgrounds

#### Visualization
Prompt: Wearing a red suit at Cannes|
:-----:|
![Visualization](assets/images/replacement.png)|

### Multi-People Image Generation
A few weeks of work on group photo generation with personalized DreamBooth weights.

#### Sample Prompts and Results
**Fantasy Theme:**
Positive: fantasy themed portrait of {token} with a unicorn horn party hat, vibrant rich colors, pink and blue mist, rainbow, magical atmosphere, drawing by ilya kuvshinov:1.0, Miho Hirano, Makoto Shinkai, Albert Lynch, 2D

**Caricature Style:**
Positive: digital oil painting of {token} (with a comically large head:1.2), big forehead, (fisheye:1.1), unrealistic proportions, portrait, caricature, closeup, rich vibrant colors, ambient lighting, 4k, HQ, concept art, illustration, ilya kuvshinov, lois van baarle, rossdraws, detailed, trending on artstation

#### Results
| ![Image1](assets/images/group_dream_1.png)| ![Image2](assets/images/group_dream_2.png)| ![Image3](assets/images/group_dream_3.png)|
|-|-|-|
| ![Image4](assets/images/group_caricature_1.png)| ![Image5](assets/images/group_caricature_2.png)| ![Image6](assets/images/group_caricature_3.png)|

### Technical Components
- **CLIP Seg**: Semantic segmentation for image understanding
- **Background Matting**: Advanced background removal techniques
- **ControlNet**: Precise control over diffusion model generation
- **DreamBooth**: Personalized model fine-tuning

## Business Impact

### Market Position
- **Early Adopter**: Among the first to commercialize DreamBooth technology
- **Quality Focus**: Emphasis on realistic, high-quality image generation
- **User Experience**: Seamless interface for non-technical users
- **Scalability**: Production-ready infrastructure for growth

### Technical Innovation
- **Realistic Generation**: Achieving high-quality realistic images
- **Production Deployment**: Moving from research to scalable production
- **Cost Optimization**: Efficient cloud infrastructure management
- **Multi-Person Generation**: Advanced group photo generation capabilities

## Learning Outcomes

### Technical Skills
- Advanced diffusion model fine-tuning
- Production ML infrastructure design
- Cloud architecture and optimization
- Startup development and scaling

### Business Experience
- Product development from concept to production
- User experience design for AI applications
- Cost optimization and resource management
- Market positioning and competitive analysis

## Future Directions

- Integration with more advanced diffusion models
- Expansion to video generation capabilities
- Mobile app development for broader accessibility
- Enterprise solutions for professional use cases

## Tags

- **Startup**: Entrepreneurial venture in AI technology
- **Diffusion Models**: Advanced generative AI architecture
- **Generative AI**: Artificial intelligence for content creation
- **DreamBooth**: Fine-tuning technique for personalized generation
- **Stable Diffusion**: Open-source diffusion model
- **Production**: Moving from research to scalable deployment
- **AWS**: Amazon Web Services cloud infrastructure
