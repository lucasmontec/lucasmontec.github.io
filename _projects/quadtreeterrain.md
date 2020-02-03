---
name: Dynamic quadtree terrain
type: Experiment

# Listing settings

direct_link: http://lucasmontec.github.io/TerrainGeneration/

font_awesome_icon: fa-flask

one_liner: An experiment to generate terrain (and modify it) via quadtrees.
description: |
    A quadtree terrain with a physics bounds generator. Press mouse 1 to paint terrain and mouse 2 to spawn balls.
    
# Main site settings

main_image: /assets/images/terrain.png
---

A quadtree terrain with a physics bounds generator. Press mouse 1 to paint terrain and mouse 2 to spawn balls (they spawn in physics sleep mode).

This was a project I did to understand other functionalities a quadtree can provide. When I was young I played a lof of worms armageddon and I was fascinated with their terrain system. I couldn´t understand how you could have something solid that reacts to gameplay and still modify it. Because of that I wanted to try to create my own system as soon as I was knowledgeable enough.

The project source code is available [here](https://github.com/lucasmontec/TerrainGeneration). It is a bit old but it still works (with exception to the keyboard detection). It uses GWT and java. I know, GWT seems to be dead.
