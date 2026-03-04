---
layout:     post
title:      "For How Much?"
subtitle:   "A party game we built in 48 hours during a weekend in Chartres"
date:       2025-05-18 12:00:00
author:     "Clement Wang"
header-img: "/img/posts/2026/for_how_much/question_page.png"
header-mask: 0.4
catalog: true
published: true
tags:
    - Game
    - Backend
    - Mobile Development
---

## The story

This one’s a bit different from my usual posts. Sometimes you just do something ridiculous with friends and see what sticks.

I had my permanent job for already 6 months as a data scientist and I’d been feeling the need to actually *build* something, so two friends and I planned a weekend away with a twist: we’d build something from scratch while we were there. One of them is a project manager, the other a software engineer. We’re the kind of people who get bored if we’re not building or planning something. So we picked **Chartres**, a small city in the center of France, and decided we’d enjoy the town *and* ship a project in less than 48 hours.

<figure class="paris-chartres-map" style="margin: 1.5em 0;">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    .paris-chartres-map #map-paris-chartres {
      height: 420px; width: 100%; border-radius: 12px;
      border: 1px solid rgba(0,0,0,.1); box-shadow: 0 4px 24px rgba(0,0,0,.1);
    }
    .paris-chartres-map .pc-info {
      background: #fff; color: #1e293b; padding: 12px 16px; border-radius: 12px;
      box-shadow: 0 2px 16px rgba(0,0,0,.12); font-size: 14px; line-height: 1.5;
      border: 1px solid rgba(0,0,0,.08);
    }
    .paris-chartres-map .pc-info b:first-child { color: #0f766e; font-size: 15px; }
    .paris-chartres-map .pc-info .distance { color: #475569; margin-top: 4px; }
    .paris-chartres-map .leaflet-control-attribution { font-size: 10px; opacity: .85; }
  </style>
  <div id="map-paris-chartres"></div>
  <figcaption style="margin-top: 0.5em; font-size: 0.9em; color: #666;">Paris → Chartres (straight-line distance).</figcaption>
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    (function() {
      var paris = [48.8566, 2.3522];
      var chartres = [48.4469, 1.4890];
      var map = L.map('map-paris-chartres', { zoomControl: true });
      L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      }).addTo(map);
      L.marker(paris).addTo(map).bindPopup('<b>Paris</b>');
      L.marker(chartres).addTo(map).bindPopup('<b>Chartres</b>');
      var line = L.polyline([paris, chartres], { color: '#0f766e', weight: 4, opacity: 0.9 }).addTo(map);
      map.fitBounds(line.getBounds().pad(0.25));
      function haversineKm(a, b) {
        var toRad = function(d) { return d * Math.PI / 180; };
        var R = 6371, dLat = toRad(b[0]-a[0]), dLon = toRad(b[1]-a[1]);
        var lat1 = toRad(a[0]), lat2 = toRad(b[0]);
        var s = Math.sin(dLat/2)*Math.sin(dLat/2) + Math.cos(lat1)*Math.cos(lat2)*Math.sin(dLon/2)*Math.sin(dLon/2);
        return 2 * R * Math.asin(Math.sqrt(s));
      }
      var d = haversineKm(paris, chartres);
      var info = L.control({ position: 'topright' });
      info.onAdd = function() {
        var div = L.DomUtil.create('div', 'pc-info');
        div.innerHTML = '<b>Paris → Chartres</b><br/><span class="distance">Straight-line distance: <b>' + d.toFixed(1) + ' km</b></span>';
        return div;
      };
      info.addTo(map);
      L.control.scale({ metric: true, imperial: false }).addTo(map);
    })();
  </script>
</figure>

When we showed up on Friday night, we started brainstorming. The idea we actually wanted was **social media analytics for ourselves**: how many hours we waste on TikTok, Instagram, YouTube, what themes we watch the most, etc. We spent a few hours on it and gave up around 10pm. Getting data out of those platforms is basically a brick wall. APIs are locked down, scraping is a mess, and we weren’t about to spend the weekend reverse‑engineering Instagram. So much for that.

We had a hard time finding another idea we liked. So we went with the dumb one: **For How Much?** You know the game. Someone asks: “For how much would you [do something insane]?” and everyone has to answer with a number. *For how much would you answer every question honestly for a week?* *For how much would you eat only mustard for a month?* That kind of thing. We figured we could make it into a real app, pass one phone around, and actually play it that weekend.

<img src="/img/posts/2026/for_how_much/question_page.png" alt="Question page" style="max-width: 40%; display: block; margin: 1em auto;">

## How the game works

We wanted it dead simple and actually playable with a group. So the whole thing runs on **one phone** that gets passed around. No accounts, no syncing. Just “your turn, type your answer, hand it to the next person.” At the end of the round you see everyone’s answers, **anonymous**, plus the **average**. We also highlight the answer that’s **furthest from the average** so there’s always one person who’s either a psychopath or a saint, and the rest of the group gets to argue about who it is. It’s low stakes, a bit silly, and it actually sparks good conversations (and some very questionable honesty).

<img src="/img/posts/2026/for_how_much/comparison_page.png" alt="Comparison page" style="max-width: 40%; display: block; margin: 1em auto;">

## The question database

We didn’t write 282 questions by hand. We used **ChatGPT**: “Give us 10 questions in category X,” then we’d skim, keep the good ones, throw out the bland or weird ones, and repeat. After a bunch of rounds we had **282 questions** in **20 categories**. A few of them:

- **Absurd**, **Deep**, **Edgy**, **Ethics**: for when you want to get philosophical or unhinged  
- **Food**, **Habits**, **Health**, **Sport**, **Travel**: classic “how far would you go” stuff  
- **Career & Lifestyle**, **Childhood & Family**, **Relationships**: good for learning how your friends think  
- **NSFW / Spicy**, **Trashy**: we’re adults, it’s a party game  
- **Creativity & Skills**, **Mind & Perception**, **Nature**, **Series / Films**, **Socials**, **World Impact / Legacy**: so there’s something for every mood  

Some of ChatGPT’s suggestions were unusable (too vague or too dark). The rest gave us enough variety that you can play for a long time without repeating the same vibe.

A few examples of questions:
- For how much would you marry someone your parents picked? (Childhood & Family)
- For how much would you be drunk in a serious meeting? (Trashy)
- For how much would you flirt with someone you hate? (Trashy)
- For how much would you stop lying for the rest of your life? (Deep)
- For how much would you separate your personal life and your professionnal life like in Severance? (Series / Films)


## Tech stack

**Backend**: **Python**, **FastAPI**, **SQLAlchemy**, **MySQL**. We didn’t need anything fancy: one device at a time, no real concurrency, so a simple API and a local DB were enough. No auth, no scaling. Just “give me a question” and “save these answers.” It was refreshing to build something that didn’t need to be bulletproof.

**Frontend**: **React Native** with **Expo**. We ran it on our phones via **Expo Go** so we could test in real time. I hadn’t touched mobile in about 10 years when I started coding for fun during high school. Back then I found Android Studio painful and front-end code boring. This time, with **Cursor** and modern tooling, it was actually enjoyable. Things have changed a lot; we had a working app in 48 hours without wanting to throw the laptop out the window.


## Conclusion

We visited Chartres, built a working game, and had a great weekend. The app did what we wanted: one phone, pass it around, anonymous answers, average, and one designated outlier to blame. If you’re ever in the mood to build something silly with friends in a weekend, “For how much would you?” is a surprisingly solid format, and way easier to ship than social media analytics.


## Some links

- **Backend:** [clementw168/for-how-much](https://github.com/clementw168/for-how-much)
- **Frontend:** [assanediouf18/ChartresFront](https://github.com/assanediouf18/ChartresFront)
- **The presentation deck:**  [Presentation deck](/assets/posts/for_how_much_deck.pdf)
