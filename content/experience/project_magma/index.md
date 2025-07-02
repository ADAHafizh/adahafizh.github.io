---
title: "TEAM MAGMA | Virtual Concert"
date: 2025-12-10
tags: ["Mixed Reality", "Interactive Media", "Performative"]
author: "Ahmad Dahlan Hafizh"
description: "Virtual Concert" 
summary: "Immerse yourself in a neon lit realm where three skeletal musicians unite to deliver a transcendent concert experience" 
cover:
    image: "banner.png"
    alt: "© Ahmad Dahlan Hafizh"
    relative: true
editPost:
    URL: ""
    Text: ""
showToc: true
disableAnchoredHeadings: false

---
## Disclaimer

> *The way information is shown on this map does not reflect any political stance or opinion about the legal status of any region, boundary, or authority. The data provided, including those from UNOSAT (United Nations Satellite Centre) and HOTOSM (Humanitarian OpenStreetMap Team), is for informational purposes only. Responsibility for how this map is interpreted or used lies entirely with the user.*

## Description 

##### Development Time: 2 Weeks

I came across HOT (Humanitarian OpenStreetMap Team) during my work as a research assistant on campus. HOT is an international team dedicated to humanitarian action and community development through open mapping. They work to provide map data which revolutionises disaster management, reduces risks, and contributes to achievement of the Sustainable Development Goals.

For this project, I intend to create a layered timeline progressive interactive map. In other words, I would like to display a map that the user can 'play around' with the different settings that allows broader range of interpretations. 

Thus, this project is a culmination and display some skills that I have learned throughout my time as a researcher.

## Demo 

**put .GIF here**

## Interactive Map 



## Processes

### HOTOSM

##### Data Collection

Originally, I wanted to use UNOSAT's comprehensive data regarding the different types of layers they provide (i.e population, agriculture). However, a major challenge that I encountered was that the data they provided were in the form of GDTable, which was incompatible with the tool I intend to use: [kepler.gl](https://kepler.gl/demo)

> **Hence, for the data, I extracted it from HOTOSM's [Export Tool](https://export.hotosm.org/v3/exports/new).**

##### Examining the Data 

After selecting the tags that I needed, I inserted the 300 - 500 MB GeoJSON file into Kepler. Examining the map at firsthand, I noticed several problems with how the tagging displays the information:

- While certain *building* types exist, only a handful of them were able to be recognized. Many of the buildings are categorized into a bool data type, that is, *building: yes.*
- This results in 'blocks' of building data that are abundant. 
- 