---
layout:     post
title:      "ViaRézo - Tech Student Association of CentraleSupélec"
subtitle:   "My first steps in a tech environment"
date:       2021-05-01 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/banners/viarezo.jpg"
catalog: true
published: true
tags:
    - Student organization
    - Development
    - Infrastructure
    - Git
---

## About ViaRézo

[ViaRézo](https://viarezo.fr/) is the tech student association of CentraleSupélec. It provides internet access and many web services (mailing lists, VMs, social media, etc.) to more than 2000 students. About 20 members with 4 board members and 4 roots.

Each year, ViaRézo gives beginner courses on various technologies to encourage students to get involved in the association. They cover web dev, infrastructure, networking, security, monitoring, etc.

A fun fact: Jean-Baptiste Kempf, who served as VIA's Vice-President (ViaRézo's predecessor), created VLC Media Player during his time there. He is now recognized as the CTO of [Scaleway](https://www.scaleway.com/en/).

I joined ViaRézo at the same time as [Automatants](https://automatants.cs-campus.fr/) (the AI student association of CentraleSupélec) but I gradually left ViaRézo because of the lack of theoretical challenge.

## Technical Infrastructure

Disclaimer: I am writing this when I already quit ViaRézo, so I may not be up to date with all services but this represents my current understanding of the infrastructure and services by ViaRézo.

### Internet Access Management
ViaRézo sets up and maintains the network infrastructure between Renater, the internet access provider in Paris, to the housing areas of Paris-Saclay, managing everything in between: router, switch, cables, WiFi terminals, etc. They manage all the IP addresses, DHCP, DNS, NAT, etc. and handle the subscription service: authentication and billing services.

### Other Services
- Form Service like Google Form but with a lot of features and customizations
- Mailing lists
- GitLab
- Carpooling service
- Virtual Machines for students with OpenStack

## My Contributions and Learning Experience

I followed ViaRézo's trainings on a lot of subjects and it clearly helped me later in my career to have a broad overview of the tech stack and the different aspects of technology. I worked on two main projects.

### Redesigning the workflow of the subscription microservice webapp

I do not know how I got into this one. We were a group of five beginners working on that one with two experienced students to help us. Ultimately, I was the only one who kept working on it. I just created a branch to have a main branch, a staging branch and several features development branches. It helped me a lot to understand what a workflow is and how Git branches work.

Since there was no CI/CD, I also wrote the GitLab actions to lint and format the code and deploy it on the staging and master environments.

We had a lot of meetings at the beginning of the project to discuss what to do and who would do it. Most people were listening to the instructions but no one really took any action. I was the same. I did not feel confident to do anything. And then at some point, I just did everything alone since no one was bothering. That's about when I realized that I should not be afraid of taking actions for myself.

### Automatic mail classification

This is another project that I was assigned to later on, because other members saw that I had more affinity with machine learning.

I did not know a lot about machine learning at that time, especially not about text classification. At some point, we had to work on how to get the emails. Since I was not interested in that part, I let someone else take the lead on it. Even though I tried to pressure him (he was a good friend though), he did not take the time to do it. At that moment, I had a lot going on at the same time since I was elected as President of Automatants, the AI student association. We were three people on that project. And then the project got abandoned slowly. I kind of regret not having taken the lead on it. Now that I have some experience, it would have been fun to make that work even if I had to do it alone.

## What I learned at ViaRézo in soft skills

### Team work and collaboration

Anything is possible with a small group of passionate people. It was crazy that ViaRézo managed the whole internet service for 2,000 people every year from wiring to the web services to subscribe to the internet. I also had the opportunity to see them wire a new building on the campus.

A lot of projects were going on at the same time, some were experts at wiring and hardware, others preferred full stack and worked on [LinkCS](https://apps.apple.com/fr/app/linkcs/id1626130016?l=en) and the other web services.

### Communication, project management and charisma

I learned a lot about teamwork spirit and communication. Since ViaRézo was a 20-people association, we had to be very efficient and communicate a lot. It was organized with a board of 4 members and 4 roots. The board members were the politicians of the association, being elected by the members each year. They were definitely more charismatic than most, you could feel the weight of their responsibilities when they were speaking even though we were all the same age. However, they all had their very own personality: some were very rational and direct, others were more diplomatic and soft.

Each week, we also had a general assembly where we discussed the future of the association and the projects. Everyone had a voice and most decisions were taken by majority vote but board members had more weight in decision making than others. There was another group of high influence people: the roots. They were considered as the technically best people of the association. They were not elected but they were the ones who were the most involved in the association and the most knowledgeable about the technical side of the association. For each technical direction, they were consulted and helped to make the best decisions technically. I learned a lot about organization and leadership there.

## Conclusion

Even though I decided to leave ViaRézo, I am still in touch with a lot of people there and I am grateful for the experience. I learned a lot about teamwork, communication, project management and charisma. I also learned a lot about the tech stack and the different aspects of technology.