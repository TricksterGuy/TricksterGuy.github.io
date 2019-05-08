---
layout: post
title: "Picross Exporter"
description: Turn images into harder, more elaborate picross puzzles.
icon: fas fa-puzzle-piece
project_image: picross-exporter.png
start_date: "Mar 2014"
hidden: true
permalink: projects/picross-exporter
categories: projects
---
## What is it
Picross Exporter is a simple, desktop application for converting images into picross puzzles of four different flavors.

* Classic Picross
* Grayscale Picross
* Painting Picross
* Light Picross

I made this for an idea for a mobile game I was designing, however I don't do mobile games anymore, but it was a fun project nonetheless.

I may write a game that plays puzzles exported by this program someday.

## Inspiration

I just love picross ok! My first experience with picross was when I had a Ti-89 titanium and learned that there was a gameboy emulator for it.
One of the games I stumbled upon was [Mario's Picross](https://en.wikipedia.org/wiki/Mario%27s_Picross).
I then found the SNES version of the game [Mario's Super Picross](https://en.wikipedia.org/wiki/Mario's_Super_Picross), so much content but unfortunately never translated.

I made a rendition of the game for RPG Maker XP some odd years ago, if you google you can probably find it, but very cringe to me for me to link here.
This post is a better version of that anyway, at least for generating puzzles

## Classic Picross

If you don't know picross is a puzzle game where you try to sketch out a hidden picture using clues from the rows and columns.

Gameplay is on a grid with each row/column having a set of numbers which are clues as to which spaces are marked.  Here is an example.

**Example Puzzle**
```
+-------+---+---+---+---+---+
|       | 5 | 1 | 1 | 2 | 5 |
|       |   | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   |
+-------+---+---+---+---+---+
| 5     |   |   |   |   |   |
+-------+---+---+---+---+---+
| 1 2   |   |   |   |   |   |
+-------+---+---+---+---+---+
| 1 1 1 |   |   |   |   |   |
+-------+---+---+---+---+---+
| 1 1   |   |   |   |   |   |
+-------+---+---+---+---+---+
| 5     |   |   |   |   |   |
+-------+---+---+---+---+---+
```

Each number tells you how many sequential cells in each row/column are marked.
Spaces in between numbers means there are one more more empty tiles between the marked cells.

From those rules here's what we can do.

1. Since the width and height of the grid is `5`, any row/column that has a value `5` have all of their cells marked.
1. The row/column with clue `1 1 1` has only one possible configuration: `marked empty marked empty marked`.

So from that here's what the puzzle looks like now.

**Step 1**
```
+-------+---+---+---+---+---+
|       | 5 | 1 | 1 | 2 | 5 |
|       |   | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   |
+-------+---+---+---+---+---+
| 5     | x | x | x | x | x |
+-------+---+---+---+---+---+
| 1 2   | x |   |   |   | x |
+-------+---+---+---+---+---+
| 1 1 1 | x |   | x |   | x |
+-------+---+---+---+---+---+
| 1 1   | x |   |   |   | x |
+-------+---+---+---+---+---+
| 5     | x | x | x | x | x |
+-------+---+---+---+---+---+
```

Now if you look at this columns 1, 2, 3, and 5 are now solved
And rows 1, 3, 4, 5 are now solved.

This leaves row 2 and column 4.  If we mark the cell at (row=2, column=4) the puzzle is solved.

**The completed puzzle**
```
+-------+---+---+---+---+---+
|       | 5 | 1 | 1 | 2 | 5 |
|       |   | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   |
+-------+---+---+---+---+---+
| 5     | x | x | x | x | x |
+-------+---+---+---+---+---+
| 1 2   | x |   |   | x | x |
+-------+---+---+---+---+---+
| 1 1 1 | x |   | x |   | x |
+-------+---+---+---+---+---+
| 1 1   | x |   |   |   | x |
+-------+---+---+---+---+---+
| 5     | x | x | x | x | x |
+-------+---+---+---+---+---+
```

Easy right?

As a real example of a puzzle here's Pikachu

{% include image.html
            img="https://66.media.tumblr.com/1d710c53dddcd114b42e4781fa1c52cf/tumblr_inline_mi3fpcf9fz1roozkr.png"
            title="pikachu"
            caption="" %}

And here's the program in Classic Black/White mode.

{% include image.html
            img="/images/projects/picross-exporter.png"
            title="Classic"
            caption="" %}

## Grayscale Picross

Now to toss some more rules into the mix, introducing grayscale picross.
Here an additional number is added to the right side and bottom per row/column to give some more information to the puzzle to make the resulting solution grayscale.

This number signifies the total number of `taps` for the entire row/column, so each cell now has a level of how dark the space is filled in.
This program supports up to (3 bits) 8 shades of gray per cell.

Again referring to the pikachu image above that image as a 16x16 grayscale puzzle with 2 bits (4 shades)

{% include image.html
            img="/images/projects/picross-exporter-grayscale-2.png"
            title="grayscale 4 shades"
            caption="" %}

And here's the image as a 16x16 grayscale puzzle with 3 bits (8 shades)

{% include image.html
            img="/images/projects/picross-exporter-grayscale-3.png"
            title="grayscale 8 shades"
            caption="" %}

Note that if bits = 1 then you just have the Classic Mode puzzle.

Again the rules don't change much from the original Black and White picross game, its just this time you'll need to click on a cell multiple times.

## Painting Picross

Now throw in some color, Painting Picross is Picross with paint. The rules of mixing paints is the inspiration behind this mode.
You have only 5 paints `red`, `blue`, `yellow`, `white`, and `black` and you mix these colors in cells to solve the picross puzzle.

In execution, its just 5 picross puzzles in one, one picross puzzle for each color.
If a cell is marked in the same location on multiple layers then the colors are mixed in the final display.

As an example, I'll use the same pikachu image as above.

{% include image.html
            img="/images/projects/picross-exporter-painting-all.png"
            title="painting picross full image"
            caption="" %}

And here's just the picross puzzle for yellow

{% include image.html
            img="/images/projects/picross-exporter-painting-yellow.png"
            title="painting picross yellow layer"
            caption="" %}

So solving one of these will require you to flip between the layers!

## Light Picross

Again a colored variant of picross, but this mode combines the concepts introduced in Painting Picross and Grayscale Picross.
The only difference is we now only have 3 colors `red`, `green`, and `blue` and combining these colors work like colors of light.
With black being 0% red, green, or blue, and white being 100% red, green, and blue.

Again the shades per cell is back in this mode allowing you to have up to 512 different color combinations if bits per cell is 3.

So example time again with pikachu.

Light puzzle with 1 bits (2 shades on/off)

{% include image.html
            img="/images/projects/picross-exporter-light-1.png"
            title="light 2 shades"
            caption="" %}

Light puzzle with 2 bits (4 shades)

{% include image.html
            img="/images/projects/picross-exporter-light-2.png"
            title="light 4 shades"
            caption="" %}

Light puzzle with 3 bits (8 shades)

{% include image.html
            img="/images/projects/picross-exporter-light-3.png"
            title="light 8 shades"
            caption="" %}

## Validation
Fun fact! Given a picross puzzle the solution to it might not be unique. See below setup.

```
+-------+---+---+---+---+---+---+---+---+
|       | 8 | 1 | 1 | 1 | 1 | 1 | 1 | 8 |
|       |   | 1 | 1 | 1 | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   | 1 |   |   |
+-------+---+---+---+---+---+---+---+---+
| 8     |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1   |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1   |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1   |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 1 1   |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
| 8     |   |   |   |   |   |   |   |   |
+-------+---+---+---+---+---+---+---+---+
```

Do you see it yet?

<button data-toggle="collapse" data-target="#puzzle-solution">Solution</button>

<div id="puzzle-solution" class="collapse">
<b>Solution 1</b>
<pre>
+-------+---+---+---+---+---+---+---+---+
|       | 8 | 1 | 1 | 1 | 1 | 1 | 1 | 8 |
|       |   | 1 | 1 | 1 | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   | 1 |   |   |
+-------+---+---+---+---+---+---+---+---+
| 8     | x | x | x | x | x | x | x | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 | x |   | x |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 | x |   |   |   |   | x |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 8     | x | x | x | x | x | x | x | x |
+-------+---+---+---+---+---+---+---+---+
</pre>

<b>Solution 2</b>
<pre>
+-------+---+---+---+---+---+---+---+---+
|       | 8 | 1 | 1 | 1 | 1 | 1 | 1 | 8 |
|       |   | 1 | 1 | 1 | 1 | 1 | 1 |   |
|       |   |   | 1 |   |   | 1 |   |   |
+-------+---+---+---+---+---+---+---+---+
| 8     | x | x | x | x | x | x | x | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 | x |   |   |   |   | x |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1 1 | x |   | x |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 1 1   | x |   |   |   |   |   |   | x |
+-------+---+---+---+---+---+---+---+---+
| 8     | x | x | x | x | x | x | x | x |
+-------+---+---+---+---+---+---+---+---+
</pre>

<p>You can flip column 3 and column 6 and that arrangement would still be the same. The two dice block doesn't make a for a good puzzle.</p>
</div>

Anyway given a puzzle, the program will tell you if there is a unique solution to it, preventing this issue entirely.

## Exporting
You are able to export your puzzles in QR code format, or in [Protocol Buffer](https://developers.google.com/protocol-buffers/) format.

## Technologies used
It is a desktop application built in C++ using the [wxWidgets](http://www.wxwidgets.org/) for the UI.  The GUI was designed in [wxFormBuilder](https://sourceforge.net/projects/wxformbuilder/)

The puzzle info is serialized in the [Protocol Buffer](https://developers.google.com/protocol-buffers/) format, so a reader can be easily made by using protoc to generate the deserializer.

## Challenges
Getting the data small enough to fit on a QR code was difficult for larger puzzles, luckily protobuf serialization is very compressed.

## Accomplishments that I'm proud of
The problem of mapping the original colors of an image to the colors only used by the puzzle was done with the median cut algorithm and a preset palette.
The same code that I used in the [nin10kit](https://github.com/TricksterGuy/nin10kit) image exporter software I wrote.

## What's next
It's generally complete and it can be used, there's some little graphical glitches that I saw when making this post.
And some of the calculations for toggling cells is off.

Maybe a way to edit puzzles without creating an image first.

## Source Code
[github](https://github.com/TricksterGuy/PicrossPuzzleExporter)
