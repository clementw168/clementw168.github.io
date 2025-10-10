---
layout:     post
title:      "To The Ground - Unity Game Jam"
subtitle:   "My First Group Coding Project: 3D Horror Game in Unity"
date:       2021-02-15 12:00:00
author:     "Clement Wang"
header-img: "/img_compressed/posts/student-projects/to_the_ground.png"
catalog: true
published: true
tags:
    - Student project
    - Game
    - Unity
    - 3D Graphics
    - Team Management
    - Blender
    - Development
pride_score: 1
---


## Project Overview

This was my very first group coding project with a team of 5 people. We designed and developed a 3D horror game in Unity using C# within one week. This intensive game jam experience taught me the fundamentals of game development and team collaboration.

## Game Trailer

<div class="responsive-iframe-container">
  <iframe src="https://drive.google.com/file/d/1N7Q-E08OffNUhwCf3AvRQVnei_BoTcfR/preview" allow="autoplay"></iframe>
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

## Game Synopsis and Gameplay

You are trapped in a small mansion and need to escape. Fortunately, you found ladder pieces that can help you reach the ground. However, you are not alone in the mansion...

- **Explore the mansion to collect ladder pieces**
- **Avoid monsters by hiding or fight back with weapons**
- **Protect your escape plan**

## Download and Play

You can download the game [here](https://drive.google.com/file/d/1QAxTDq3LyYiQcaBdpUdU7sxK0e0sgb4l/view?usp=drive_link).


## Technical Details

### Game Endings

1. **Death**: The monster kills you. Game over.
2. **Ladder Destroyed**: The monster destroys your ladder before you can escape. Game over.
3. **Victory**: You collect all ladder pieces, construct the ladder in the basement, and escape to the ground. You win!
4. **Monster Slayer**: You kill all the monsters. Good job!

### Items

**Picking up items**: Some items are collectible on the map. Once picked up, they appear in your *inventory* and can be selected and used.

Here are the items available in the game:

**Flashlight**: There are very few lights in the mansion. Using the flashlight is essential to see in the dark.

**Ladder pieces**: There are 5 ladder pieces scattered around the mansion. They only appear when certain conditions are met...

**Weapons**: You can find a bat, a revolver, and a shotgun in the mansion. For the revolver and shotgun, you also need to find ammunition and reload them.

**Medkit**: You can find a medkit in the mansion to heal yourself.


### Map and Design

Most assets were imported from public sources. We wanted to create the best game possible, but time was too short to create all assets from scratch. Some simpler assets were made in Blender.


### Audio

The audio was made by Eliot Py.

### Monsters

There were three types of monsters:
- **Crawling monster**: Crawls on the ground. Slow but has a lot of HP.
- **Flying bat**: Flies in the air with chaotic movements. Fast and hard to aim at with a gun.
- **Final Boss**: Massive HP and high damage. Run if you encounter it...


There are two types of behaviors:
- **Patrolling**: The monster patrols on a fixed path.
- **Ladder destroyer**: The monster goes directly to the basement to destroy the ladder.

Whenever they see the player, they will chase and attack. We used raycasts to detect the player and simple pathfinding algorithms to move the monsters.

### Hiding in a closet

Once a monster targets the player, it will never stop chasing except if the player hides inside a closet. We added this mechanic to encourage the player to escape rather than fight, since monsters are strong. This reinforces the horror atmosphere. To further force the player to escape, the first monster appears when no weapons are available yet.


### Fighting system

For fighting, we used a hitbox system for player weapon interactions with monsters. For monster-to-player combat, we implemented this: if the monster is close enough to the player, an attack animation starts. When the animation ends, if the player is still in range, the player gets hit and loses HP. This gives the player a chance to run away.


## My Contributions

### Project Management

Since this was our very first game jam, we had a lot of ideas during the brainstorming session. I found that it wasn't very well organized : we would sometimes talk about core concepts like monster behavior and then jump to discussing where to place a chair on the map. So, I tried my best to organize the brainstorm session and put everything down into prioritized tasks on Trello. I think this helped us work together a lot, especially since we didn't even use Git to collaborate.

### Game Design

**Guided Introduction**: I'm pretty proud of this idea I had: since there were many mechanics but we wanted the player to be immersed directly in the game, information is given non-intrusively in the form of pop-up text like subtitles.

### Programming

**Collection System**: I coded the collection system: if a collectible is inside a box in front of the player, the collectible illuminates itself so the player can see it better and knows they can collect it.

**Fighting System and Animations**: I also worked on the fighting system in both directions: players hitting monsters and monsters hitting players. The hardest part was synchronizing the animations with the hitboxes.



## Thoughts

This is still one of my favorite projects to this day (in 2023). We worked really hard on it, and it was a lot of fun working with my team. From 8 AM to 12 AM, we were all together on Discord coding (since we were locked down due to the pandemic). Our only breaks were to eat, use the bathroom, and sleep.

The funny thing is that we all discovered Unity and C# one week before the game jam. Even though it is not perfect, I still find it crazy that we were able to make this game in one week with only one week of learning.

Special thanks to:
- [Guillaume Levy](https://www.linkedin.com/in/guillaume-levy-bbbb681b8/) for the map design, the original idea, and light baking
- [Leo Durand-Köllner](https://www.linkedin.com/in/leo-dk/) for the inventory management, the closet mechanic, the fighting system, and his huge help with object-oriented programming





