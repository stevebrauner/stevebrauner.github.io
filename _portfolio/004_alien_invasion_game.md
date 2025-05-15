---
layout: single
title: "Alien Invasion Game"
classes: wide
excerpt: "A pygame based game inspired by Space Invaders."
header:
  teaser: /assets/images/ai_play.png
feature_row:
  - image_path: /assets/images/ai_startup.png
    alt: "Alien Invasion game at start up"
    excerpt: "game at start up -- [view](/assets/images/ai_startup.png)"
  - image_path: /assets/images/ai_play.png
    alt: "Alien Invasion game during play"
    excerpt: "game during play -- [view](/assets/images/ai_play.png)"
---

# Alien Invasion Game

{% include feature_row %}

As part of my self-taught Python journey, I wrote a game based on the Space Invaders arcade game as in the book listed below. I then wanted to challenge myself to refactor the code to implement a Model, View, Controller design pattern.

The original code was complete and working. I had to refactor the code to make it work with the new pattern. The main challenge was to figure out how to separate the game logic, display views and control logic since the classes and methods were intertwined.

## Coding Reflections

- Originally coded this game following the chapters from _Python Crash Course,
  2nd Edition_ by Eric Matthes.
- Refactored it to implement a Model, View, Controller design pattern.
- Refactoring proved complicated due to the mixing of model, view, and controller logic in the original implementation.

## Source Code

See source code at the repo on <a href="https://github.com/stevebrauner/alien_invasion">GitHub</a>.
