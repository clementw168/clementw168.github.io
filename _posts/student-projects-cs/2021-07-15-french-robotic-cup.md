---
layout:     post
title:      "French Robotic Cup - Autonomous Robot Development"
subtitle:   "Building an Autonomous Robot for Object Manipulation in Defined Environment"
date:       2021-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/student-projects/plan_croc.png"
header-mask: 0.3
catalog: true
published: true
tags:
    - Student project
    - Robotics
    - Computer Vision
    - Development
---


## Project Overview

The French Robotic Cup (Coupe de France de Robotique) is a year-long robotics competition. Our team of 11 engineering students split into three sub-teams: one on the robot's movement, one on the interaction system (getting cups onto the board), and one on vision, where I worked, alongside one older student and one student in my own year.

Our robot           | Competition arena
:-------------------------:|:-------------------------:
![Photo of our robot](/img_compressed/posts/student-projects/croc_1.jpg)  |  ![Photo of the playground](/img_compressed/posts/student-projects/croc_2.jpg)

## The vision system

The setup was a single overhead camera above the arena, giving a bird's-eye view of the whole board. My part was Aruco marker detection: each robot carried a marker on top for identification and tracking, and reference markers placed around the arena gave us the calibration points to convert image coordinates into real-world positions. Technically, this part wasn't very interesting. Aruco detection is easy, it's mostly just calling functions from OpenCV.

## What actually happened

I didn't enjoy this project that much overall. There were real organizational problems. The upperclassmen who were supposed to lead us had gone through COVID the year before, so they hadn't gotten to build a robot themselves either. That meant there was no clear direction handed down, and nobody who'd actually done this before to unblock us when we got stuck. I wanted to contribute more, but I was too inexperienced to help fix the organization itself, and I spent a lot of the year feeling like a small cog with no clear job.

It was also the first project I'd worked on with that many interacting components. Movement, interaction, and vision all had to work together, and coordinating across three sub-teams turned out to be much harder than any of the individual parts.

By the end of the year, a lot was still missing. The robot could move, but we didn't perform well at the competition.

What I did love was the people. Everyone on the team was genuinely cool to work with, and I spent a lot of time just watching others do things I'd never seen before: how servo motors work, how to print an electronic plate, how voltage regulators work, how to use a 3D printer. I learned a lot about how a whole system comes together, even though the vision part itself did not challenge me technically.

## Takeaway

I think this is actually the project where I started to become obsessed with controlling every single piece of a pipeline before touching the code. Watching how many things could go wrong between all those components, with nobody fully in control of the whole picture, made that lesson stick.

