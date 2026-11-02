---
layout:     post
title:      "Verdant Depths"
subtitle:   "A roguelite dungeon crawler built at a game jam"
date:       2026-06-04 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/2026/verdant_depths/cover.png"
header-mask: 0.4
catalog: true
published: true
tags:
    - Game Dev
    - Python
    - Game Jam
---

Verdant Depths is a roguelite dungeon crawler I built in Python for a game jam in May 2026. Fight through 7 floors of procedurally generated forest ruins, collect perks and relics, and defeat a boss on each floor.

## Game trailer

<iframe width="100%" height="480" src="https://www.youtube.com/embed/zwXn5EEU10w" frameborder="0" allowfullscreen></iframe>

<div style="display:grid;grid-template-columns:1fr 1fr;gap:15px;margin:20px 0;">
  <img src="/img/posts/2026/verdant_depths/floor1.png" alt="Floor 1">
  <img src="/img/posts/2026/verdant_depths/floor5.png" alt="Floor 5">
</div>

<div style="display:grid;grid-template-columns:1fr 1fr;gap:15px;margin:20px 0;">
  <img src="/img/posts/2026/verdant_depths/iron_warden.png" alt="Iron Warden">
  <img src="/img/posts/2026/verdant_depths/void_sovereign.png" alt="Void Sovereign">
</div>


## The game

Clear all rooms on each floor, defeat the boss, pick a relic, and descend. 7 floors total. Reach the bottom to win.

<div style="position:relative;padding-bottom:57.81%;height:0;overflow:hidden;">
  <iframe style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" src="https://itch.io/embed-upload/17805912?color=333333" allowfullscreen></iframe>
</div>

If is does not work:

<iframe frameborder="0" src="https://itch.io/embed/4629999?linkback=true" width="552" height="167"><a href="https://clementw168.itch.io/verdant-depths">Verdant depths by clementw168</a></iframe>

### Controls

| Input | Action |
|---|---|
| ZQSD / WASD / Arrows | Move |
| Mouse | Aim |
| Left Click | Shoot arrow |
| Space | Dash (invincible while dashing) |
| Esc | Pause/Quit |

## Game modes

![Main menu](/img/posts/2026/verdant_depths/main_menu.png)

The game has three modes. **Dungeon** is the main mode: 7 floors of procedurally connected rooms, perks after combat rooms, a shop per floor, and a relic choice after each boss. Run stats and a best-run high score are tracked.

**Arena** is a practice mode. Pick any enemy or boss, an optional relic, and fight in a sealed room. No coins, no progression, no healing.

**Endless** puts you in a sealed room with infinite waves. Every 5-wave cycle rewards HP, perks, and relics. Wave 5 of each cycle spawns a boss and grants a full heal. By cycle 6, every boss wave spawns 3 bosses at once.

## Enemies and bosses

12 regular enemies unlock progressively across the 7 floors: melee chasers, teleporting casters, fast erratic bats, and slugs that drop burning patches on the floor.

![Enemies](/img/posts/2026/verdant_depths/enemies.gif)

One unique boss per floor, each with a Phase 2 triggered around 50% HP. Phase 2 adds new attacks rather than just speeding up cooldowns. The Ancient Tree gains a continuous thorn pinwheel. The Iron Warden starts charging across the room.

![Boss showcase](/img/posts/2026/verdant_depths/boss_promo.png)

![Boss in action](/img/posts/2026/verdant_depths/boss.gif)


## Perks and relics

After clearing a combat room, pick one of 3 random perks. After each floor boss, pick one of 2 relics. 12 perks and 20 relics total.

Perks are stat upgrades: piercing arrows, double shot, faster dash, larger coin pickup radius. Relics enable build synergies. **Venom Gland** + **Echoing Shot** + **Piercing Shot** turns every arrow into a poison-spreading reflected chain. **Curse of Greed** doubles coin drops but empties your wallet at the start of each floor.

![Perks](/img/posts/2026/verdant_depths/perks.png)

![Relics](/img/posts/2026/verdant_depths/relics.png)

## Context

A friend of mine, Guillaume, organized a 3-day game jam over May 24–26, 2026. Paris was in the middle of a heatwave. Guillaume invited six friends to either make something or just hang out in an open space in the center of the city. In the end most people played board games. I still wanted to build something, so I started working on a game on the side, between board game sessions.

The day after, I went to Fontainebleau to boulder on real rock, so I didn't get much done during the jam itself. The game ended up being built over two weeks of evenings after work.

I first tried Ursina Engine, a Python library for 3D game development. It wouldn't run on my Mac, so I moved to Pygame and 2D.

I spent a few hours on a game where a tourist walks around Paris, visits landmarks, and dodges sunrays. It was bad, there was no reason to keep playing. So I started over and landed on the roguelite idea: procedural content is easy to generate and gives a lot of content with little work.

## Technical highlights

**Wall-aware enemy steering.** `Enemy._steer_toward` takes 8 compass directions, scores each by dot-product with the goal vector, and subtracts a penalty for directions that hit a wall tile. The highest-scoring direction becomes the velocity. No pathfinding graph, no nav-mesh, O(1) per enemy per frame. Getting this right took several hours: enemies have circular hitboxes and kept getting stuck on wall corners.

**State machine.** The game itself is a state machine with 18 states. Each state has a dedicated event handler, update function, and draw function.

**Web deployment with pygbag.** I wanted anyone to be able to play the game without installing anything. pygbag compiles a Pygame project to WebAssembly so it runs directly in the browser. The output is a static bundle that I uploaded to itch.io, which gives the embedded player you see above.

**Game balance.** For the shop, I computed the expected number of coins per floor from the enemy count and spawn tables. I then set HP vial and perk prices so that clearing all combat rooms affords exactly one of each per floor, with prices scaling across the 7 floors. Boss HP follows the same logic: it is tuned against the player's expected damage output at that point in a run, accounting for stacked perks and relics. I probably made it too hard since that's what I personally like.

## Conclusion

I have been focused on my PhD thesis for the past few months, and this was a good break. This won't be the game of the year, but I like it quite a bit. I probably played it for more than 10 hours over the two weeks.

- [Game trailer](https://youtu.be/zwXn5EEU10w)
- [GitHub repository](https://github.com/clementw168/gamejam-may-2026)
- [Itch.io page](https://clementw168.itch.io/verdant-depths)
