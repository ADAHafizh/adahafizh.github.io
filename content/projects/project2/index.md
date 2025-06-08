---
title: "Dungeon Escapist | p5.js"
date: 2024-05-09
tags: ["Digital Video Game", "Game Development", "Game Design", "Class"]
author: "Ahmad Dahlan Hafizh"
description: "A maze game with custom gyro-controller" 
summary: "Dungeon Escapist is a single-player game where players take control of an adventurer and delve through a dungeon. The game requires an Arduino Gyroscope controller." 
cover:
    image: "bannerB.gif"
    alt: "© Camila xiao"
    relative: true
editPost:
    URL: "https://editor.p5js.org/ADAHafizh/full/-seh8SQcuh"
    Text: "Game Link (REQUIRES ARDUINO CONTROLLER - 2025)"
showToc: true
disableAnchoredHeadings: false

---

## Description 

##### Development Time: 4 Weeks
##### Featured in End of Semester Showcase

Dungeon Escapist is a single-player game where players take control of an adventurer and delve through a dungeon. By using a physical controller that reacts with tilting, players can move their character, collect coins, and reach the exit before the time runs out!

> ***Escapist (adjective)***
>
> relating to avoiding an unpleasant or boring life by thinking, reading, etc. –Cambridge Dictionary

The game is heavily inspired by older titles such as Adventure (1980), with interactive elements from The Legend of Zelda: Breath of the Wild (2017). This game is also a direct sequel to my previous game: Pyro Dancer [Pyro Dancer](https://adahafizh.github.io/projects/project1/).

Unlike the previous game, however, **Dungeon Escapist focuses more on problem-solving.** The main character, an adventurer, wishes to gain riches! He began to look around the Adventurer’s Guild to see if there were commissions. Noticing the dungeon-clearing request, our protagonist sets off to explore the uncharted areas in hopes of bathing in fame and fortune.

The game was developed as a final project for New York University Abu Dhabi (NYUAD) Interactive Media program class: Introduction to Interactive Media, lectured by Aya Riad. 

## Screenshots 

| In-game screenshots        |
| -------------------------- |
| ![Main Menu](mainmenu.png) |
| ![Game Screen 1](ss1.png)  |
| ![Game Screen 2](ss2.png)  |

## Intended Gameplay

Players will have to dodge the fireballs by going up or down. They also have the choice to speed up their running by pressing the D key. As the score increases, so does the difficulty.

Above a certain score, players will be greeted by stationary monsters that instantly kill them upon touching. This would balance out the difficulty and create varied gameplay, as dodging only fireballs would be boring!

| Knight Sprite                    |
| -------------------------------- |
| ![Knight Sprite](knight.gif) |

To win the game, players must reach a score of 1000 and proceed to the boss battle. 

## Development

As the name suggests, Pyro Dancer will feature a knight running through a dracula-esque castle to save the princess. However, he is greeted by dozens of fireballs in the process.

##### Brainstorming Phase 

This was my very first take on using JavaScript, p5, and making a game. I wanted to make an "8-bit" endless runner game because of my inspiration from older titles. Plus, it would make a nice presentation as it is very thematic. 

| Sketches            |
| -------------------------------- |
| ![Sketch](sketch.jpeg) |

##### Programming Phase

In order for me to make this game, I used an external library called p5.Play, an extensive game-oriented packed with QoL features. In my code, I used this package mostly for sprite animations for the knight and fireball. The package allowed me to also easily make the main menus and buttons. 

+ Building upon my previous knowledge from Computer Science classes, I heavily utilized OOPs, Classes, Parent-Child inheritance to easily make the objects inside the game. 

##### Shortcomings

Because of the tight deadlines, I was unable to actualize the boss fights and combat mechanics. There were major bugs in the development process that was caused by a certain version of p5.play incompatible with p5. 

## Conclusion & Insights 

Pyro Dancer was my very first video game that I made. It introduced me to the 'surface' level of game development and design pipeline. 

>Because of this, I truly found a passion, hobby, and pathway that I enjoyed. Being a developer and designer requires one to have a mind to approach things in various ways. 

