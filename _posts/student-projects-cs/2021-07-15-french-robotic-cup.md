---
layout:     post
title:      "French Robotic Cup - Autonomous Robot Development"
subtitle:   "Building an Autonomous Robot for Object Manipulation in Defined Environment"
date:       2021-07-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/student-projects/plan_croc.png"
catalog: true
published: true
tags:
    - Student project
    - Robotics
    - Computer Vision
    - Development
---


## Project Overview

The French Robotic Cup (Coupe de France de Robotique) is an annual competition that challenges teams to build autonomous robots capable of performing complex tasks in a structured environment. Our team of 11 engineering students spent approximately one year developing a fully autonomous robot designed to navigate a defined arena and manipulate objects according to the competition's specific requirements.

This comprehensive project integrated multiple engineering disciplines, including mechanical design, computer vision, autonomous navigation, and real-time control systems. The competition provided an excellent opportunity to apply theoretical knowledge to a practical, time-constrained engineering challenge.

## Robot and Environment

Our robot           | Competition arena
:-------------------------:|:-------------------------:
![Photo of our robot](/img_compressed/posts/student-projects/croc_1.jpg)  |  ![Photo of the playground](/img_compressed/posts/student-projects/croc_2.jpg)

The competition arena featured a structured environment with specific zones, obstacles, and target objects that robots needed to identify and manipulate. Our robot was equipped with multiple sensors, including cameras and a LiDAR, to navigate and interact with the environment autonomously.

## Technical Contributions

I was responsible for developing the visual perception system that enabled our robot to understand its environment and locate objects of interest.

### Vision System Architecture

The system utilized a single overhead camera positioned above the competition arena, providing a bird's-eye view of the entire playing field. This setup offered several advantages:
- **Complete environmental awareness**: The omniscient perspective eliminated blind spots
- **Simplified coordinate mapping**: Direct transformation from image coordinates to world coordinates
- **Real-time processing**: Single camera reduced computational overhead

### Aruco Marker Detection and Localization

The core of my contribution involved implementing robust Aruco marker detection and interpretation:

- **Robot identification**: Each robot had a unique Aruco marker on its top surface, enabling precise identification and tracking
- **Environmental calibration**: Strategic placement of reference markers throughout the arena provided spatial calibration points

From these, I could get the position of the robot in the arena.

