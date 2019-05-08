---
layout: post
title: "Tilemap Editor"
description: Longest running project, needs a better name... meh.
icon: fas fa-map
image: tilemap-editor.png
start_date: "Sept 2009"
hidden: true
permalink: projects/tilemap-editor
categories: projects
---
## What is it
Tilemap Editor desktop application for making 2D tile maps of various styles.

## Inspiration
RPG Maker XP, was the inspiration, and many features of the program are features of the mapping system of RMXP.
I eventually left that community when VX came out as it offered nothing new in terms of the RGSS library (pretty much RPG Maker's internal multimedia API).

## History
This is the longest running program I have been working on predating even the educational software I wrote as a TA. I started back in 2009 as a way to learn C++ with a big software project.
The program exists in two versions, one with the old codebase that I did a release for My Senior Design Capstone Project in Fall 2010. The program was to be used for Gameboy Development, as that was the purpose of the Capstone Project, to adapt the work I already done for the project for use with the Gameboy Advance.
I took plenty of screenshots as a history of how the software evolved. However the free hosting I had provided by an online friend went down permanently and thus I lost all of them, 45 images of the history of the program lost.

There is a download link with the "old codebase" at the bottom of this post. Its pretty complete.

At around 2013-14ish I decided to scrap all of the code I have done as the design of the program made it hard to add new features. I wanted to get better at C++ so I would make big refactors and pull code in one module at a time.
Another reason was the original program was Windows only, and does some weird interfacing with Graphics libraries and wxWidgets, I wanted a purely wxWidgets solution. This is still an ongoing work, as I get better with C++.

## Screenshots
Note due to losing my former host these screenshots are of the new WIP codebase.

{% include image.html
            img="/images/projects/tilemap-editor.png"
            title="Map with Background"
            caption="Map with 2 layers and an autoscrolling background" %}

{% include image.html
            img="/images/projects/tilemap-editor-2.png"
            title="Map with Background Layer Rotated"
            caption="Map with 3 layers (one of them rotated) and an autoscrolling background" %}

## Features
1. Map System
    * Ability to export maps
        1) GBA (partially complete)
        2) txt
        3) xml
        4) images
    * Ability to import maps
        1) txt
        2) xml
        3) images
    * Map types
        1) rectangular
        2) isometric (planned)
        3) hexagonal (planned)
    * Maps are editable by layer (and can have infinite layers)
        1) Transformations can be applied to layers
    * Map backgrounds are editable (and may be scrolling)
    * Support for animated tiles
    * Support for "auto tiles" (planned)
    * Support for multiple tilesets (planned)
    * Backgrounds can:
        1) not scroll
        2) scroll with camera
        3) automatic scroll
        4) draw once or repeating
    * Support for collision layers
        * Map Based
            * Collision for each tile on map
            * Collision based on each pixel (partially implemented)
            * Direction based collision info per tile on map (planned)
        * Tile Based (planned)
            * Collision info associated with each tile in tileset
            * Collision based on each pixel for each tile in tileset
            * Direction based collision info per tile in tileset
2. GUI
    * Viewing operators
        1) zooming (map and tileset)
        2) layer visibility
        3) grid lines
        4) dim lower layers
    * Tools:
        1) pencil - draws a set of tiles
        2) eraser - erases a set of tiles
        3) line - draws tiles in a line
        4) rectangle - draws a rectangular area of tiles
        5) circle - draws a circular area of tiles
        6) fill - flood fill a set of tiles
        7) replace tile - replace a tile with another
        8) select - select tiles on map and do various things with them
    * Ability to edit
        1) map properties
        2) layer
        3) backgrounds
        4) collision layer
        5) animated tiles
        6) autotiles (planned)
    * Can view multiple maps simultaneously without seperate instances of the program.
    * Ability to playtest the map
    * Ability to select tiles from tileset and place on map
    * Ability to create brushes from tiles in the tileset. (planned)
3. Plugin System (planned)
    * Plugins may
        1) add data to maps
        2) add new tools / menu options
        3) new export formats
        4) add rendering code
    * Plugin Manager to add, update, remove, enable, and disable plugins

## Technologies used
It is a desktop application built in C++ using the [wxWidgets](http://www.wxwidgets.org/) for the UI.  The GUI was designed in [wxFormBuilder](https://sourceforge.net/projects/wxformbuilder/)

The save data format is a proprietary binary format, that's clearly documented in the User Manual, you can also export to images, xml, and a txt document.

## Challenges
Managing a big codebase and keeping the design clean is a big challenge! Cross platform development is pretty challenging especially if you want to do some interfacing between a multimedia library and GUI library.

And feel kinda bad, a ton of missed opportunities in the past 10 years, due to school and subsequently work taking up more time.

## Accomplishments that I'm proud of
The sheer amount of time I put into this one.

## What's next
Still a ton of work to be done to be feature parity with the old codebase, and wish I could spend an hour or two a day (or even a week) on this given that its been just about 10 years now.

The old codebase is functional, and you can use it to make 2D rectangular tilemaps with an optional collision layer. The program runs well in Wine for non windows based systems.

## Source Code (New Codebase)
[github](https://github.com/TricksterGuy/TileMapEditor)

## Download (Old Codebase)
[google drive](https://drive.google.com/open?id=0B6g7zcZaFwPTYi1xTXBFcW5aZDA)
