---
layout:     post
title:      "Photogen AI - Founding a Startup on Diffusion Models"
subtitle:   "From Research to Production: AI-Generated Images for Customers"
date:       2023-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/gap_year/photogen_dark.png"
catalog: true
published: true
tags:
    - Gap year
    - Startup
    - Computer Vision
    - Image Generation
    - Diffusion Models
    - AWS
    - Development
    - Infrastructure
pride_score: 2
---

## Startup Journey  

The idea for **Photogen AI** came during my gap year. After an internship in a US startup, I wanted to try building something myself. At the same time, **Generative AI** was exploding. When a friend suggested starting a project together, we jumped in and decided to launch a company around it.  

The concept was simple but ambitious: allow customers to generate **realistic, high-quality photos of themselves** with AI. At the time, dozens of “AI avatar” apps were popping up, but none were producing results that looked professional. That gap became our opportunity.  

I joined the adventure at the end of **December 2022**, and by **February 2023**, we had launched our first app. From there, we worked on communication and marketing, invested in ads, and started talking to early customers. The traction was rather low, and by **April 2023** we realized that a pure B2C might not be a good idea for us. We decided to pivot toward **B2B collaborations**, working with other companies that wanted to integrate our AI technology. We started discussions with one, did some work, but negotiations stalled. By **June 2023**, we decided to shut down the company and move on to other projects.

At **Photogen AI**, I was responsible for the **core technology**. Our team was small and focused: three developers on the app, one person on marketing, and myself as the ML and MLOps engineer. I worked on fine-tuning diffusion models for each customer, building the inference pipeline, and pushing forward the R&D that powered the product.


All of this happened while I was still doing my internships during the day. It often meant working late into the night on Photogen, which was exhausting at times but also incredibly exciting.  

Looking back, it was an intense six-month journey: launching fast, iterating, pivoting, and finally deciding to stop. Even though Photogen AI didn’t last, the experience taught me a lot about moving from research to production, building under pressure, and what it takes to transform cutting-edge AI into an actual product.

Here is an interview about Photogen AI:  

<div class="responsive-iframe-container">
  <iframe src="https://drive.google.com/file/d/1XFjtlFAM181U34I01PUaqXSWS_m2X7Vg/preview" allow="autoplay"></iframe>
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


## Technical Highlights  

### DreamBooth for Realistic Images  

When [DreamBooth (CVPR 2023)](https://arxiv.org/abs/2208.12242) came out, most apps used it to create cartoonish or stylized avatars. We pushed the method toward **realistic, photorealistic results**.  

With the right fine-tuning tricks, we managed to get results that felt like actual photos rather than AI caricatures:  

<style>
.img-gallery-4 {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px;
  margin: 20px 0;
}

.img-gallery-4 img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 6px;
  display: block;
}

.img-gallery-4 figure {
  margin: 0;
}

.img-gallery-4 figcaption {
  text-align: center;
  font-size: 0.9em;
  color: #666;
  margin-top: 8px;
}
</style>

<div class="img-gallery-4">
  <figure>
    <img src="/img_compressed/posts/gap_year/in_front_of_the_eiffel_tower.jpg" alt="In front of the Eiffel Tower">
    <figcaption>In front of the Eiffel Tower</figcaption>
  </figure>
  <figure>
    <img src="/img_compressed/posts/gap_year/in_front_of_the_kremlin.jpg" alt="In front of the Kremlin">
    <figcaption>In front of the Kremlin</figcaption>
  </figure>
  <figure>
    <img src="/img_compressed/posts/gap_year/in_rome.jpg" alt="In Rome">
    <figcaption>In Rome</figcaption>
  </figure>
  <figure>
    <img src="/img_compressed/posts/gap_year/professional_picture.jpg" alt="Professional Picture">
    <figcaption>Professional Picture</figcaption>
  </figure>
</div>



### AWS Infrastructure & Scaling  

One of the hardest challenges was moving from **Google Colab experiments** to **production-ready AWS pipelines**.  

- **Inference pipeline:** built with an autoscaling group that monitors SQS queues, keeping warm instances ready for peak demand.  
- **Training pipeline:** DreamBooth fine-tuning jobs running on **AWS Batch**, containerized with Docker and served via FastAPI.  

We also set up monitoring dashboards, error alerts, and cost optimizations to keep the business sustainable.  

AWS Dashboard|  
:-----:|  
![AWS Dashboard](/img_compressed/posts/gap_year/aws.png)|  


### Paris GenAI Hackathon  

We also joined the **Paris GenAI Hackathon**, working on how to **reduce the number of images required for DreamBooth fine-tuning**.  

This turned into a mix of **literature review and experiments** with the latest models in:  
- Pose transfer  
- InstructPix2Pix  
- Lighting adaptation  
- Background matting  

Example result (Prompt: *Wearing a red suit at Cannes*):  

Visualization|  
:-----:|  
![Visualization](/img_compressed/posts/gap_year/replacement.png)|  


### Multi-Person Image Generation  

Another research direction was **group photo generation**. This required merging multiple DreamBooth embeddings, handling segmentation, and conditioning models like **CLIPSeg and ControlNet**.  

Here are some outputs:  

| ![Image1](/img_compressed/posts/gap_year/group_dream_1.png)| ![Image2](/img_compressed/posts/gap_year/group_dream_2.png)| ![Image3](/img_compressed/posts/gap_year/group_dream_3.png)|  
|-|-|-|  
| ![Image4](/img_compressed/posts/gap_year/group_caricature_1.png)| ![Image5](/img_compressed/posts/gap_year/group_caricature_2.png)| ![Image6](/img_compressed/posts/gap_year/group_caricature_3.png)|  


## Reflections  

Founding **Photogen AI** was my first dive into entrepreneurship. Beyond the technical excitement, it was about **building a product, serving users, and putting research into production**.  

I realized that moving from research papers to a working business requires much more than just clever code: you need infrastructure, user experience, scalability, and cost control. I guess our biggest mistake was to not have a clear business plan and to build the product early without having any customers.


It was a short but intense adventure, and one of the most valuable learning experiences of my gap year.  
