---
layout: post
title: Scroll Down Memory Lane Episode 1 - Ti Calculator Games
description: Yup I remember my 10th/11th grade Lit teacher yelling at me to put my calculator away :^)
icon: fas fa-calculator icon-text-gray icon-bg-pale-blue
categories: programming
tags: memory-lane-episodes
---

Yeah in this series of posts Brandon reviews past projects, the first post in this series is one of my first works. A Ti-86 game by the name of Yahtz.
I still owe this blog my history of how I got into programming in Day-At-GT-Catalyst!, maybe this will appease those people if they exist until I can perform a
deep dive of everything.

## Overview

The year was 2005, senior year high school. I was an easy target for bullies despite being big and tall. I was a very shy person sometimes going days without
saying a word to anybody. Just about the only time I spoke was to answer a question. Heck people almost started paying me to hear me speak. But yeah weird spot
where no one wants to hang out with you, too smart so too different from other kids including other smart kids. I was known as the human calculator too,
Academic team every 5th question was a math question and I was the quickest to solve.

I was a very different Brandon back in the day. Most people wouldn't even know...

Anywho due to all of this I spent the period before homeroom and the first two periods in Technology + Drafting class. Authur Workman was the teacher and pretty
much let me do what I wanted. Whether is help manage the crappy computers in the lab, or program stuff. In fact I spent most of the day programming on my Ti
Calculator given to me by the school, surprised they even had money for 50 graphing calculators TI-86's and they let us have them until the end of the year,
gifted benefit I guess. But still school in the middle of nowhere rural area Georgia.

## Ti-Calculators

So as a preview to the big answer to the how did you get into programming Brandon question. This was my 4th experience with programming. Fortunately I do have
records and stuff produced starting with this experience programming.

This sparked after my very first experience with BASIC at 8 years old, TI-Basic was quite similar so it was very easy for me to pick it up.

However...

Some of the graphing calculators in class had real neat programs. I'm sure most people who will read this remember games like Phoenix, BlockDude, and Mario with
that level editor. I wanted to make real neat games, and that's when I discovered they weren't written in Ti-BASIC but something called assembly.

**I hope you know where this is going yeah? Down the rabbit hole I go :^)**

## The Rabbit Hole

The Ti-86 the calculator given to me

**Specs**

* CPU: Zilog Z80[3] 6 MHz
* RAM: 128 KB, 96 KB user-accessible
* ROM: 256 KB non-upgradable
* Display: 128x64 pixels high-contrast monochrome LCD
* Data Communication: Serial link port; allows two TI-86 calculators to be connected to each other, or one TI-86 to be connected to a PC, for data transfer vi
 a special link cable
* Programming Languages: TI-BASIC, Z80 Assembly language (ASM)

Fun fact the Z80 processor is kinda similar to that used in the original Nintendo Gameboy handheld its a hybrid of that one and the Intel 8080.

So here's me with only experience with BASIC, Event programming in Game Maker and RPG Maker 2000/2003. How the heck did I learn assembly? I spent most of the
time during courses reading up on reference material about the assembly language and about binary and hexadecimal and other goodies like 2's complement.

It was a very hard frustrating experience, this was my first experience with actual low level programming and I hadn't even had formal lessons in how to
program. And yeah high school did not have a Computer Science program so everything I learned it was on my own reading material from the internet. In fact
I had found the tutorial I was reading however it doesn't appear to be hosted anywhere on the internet anymore. I should go thank the author, it did a good job
teaching assembly to someone who barely had any programming experience.

Yeah I have a bad habit of banging my head into the wall on something without asking for help. I'm quite stubborn in regards with learning. The struggle is real
and I learn best taking a problem completely apart and putting it back together. Each failure making me even more resolved to see it through to the end.

## The Program
I was eventually able to make an assembly program to make BASIC programming easier, using an existing setup as a base. You can extend Ti-Basic with
assembly by adding new functions. I don't think it caught on looking at it it only had 1000 downloads, however I used the tool to make a game from it.

The neat thing is you can also draw sprites on screen using the functions I added to Ti-Basic, even included grayscale support. So given that I give you a game
I designed and made in senior year high school. Yahtz. Its not Yahtzee, but a game played with 3 dice instead of 5 and 2 rolls of dice instead of 3.

Of course your goal is to get the high score. The rules are similar to Yahtzee except the scoring is different. At the start of the game a bonus combination
is generated if your roll ends up being the bonus combination then you score a lot of points. You have 10 rounds of rolling the dice to get the high score.

* Two of a kind
* Straight
* All odd / Even
* Three of a kind
* Bonus Roll

Now I did two versions of the game, one without the fancy assembly code and another with it. Here are some screenshots taken from
[ticalc.org](https://www.ticalc.org/archives/files/fileinfo/356/35653.html) that I did all those years ago. Its quite amazing ticalc.org is still a thing.

{% include image.html
            img="/images/2019-5-14-Scroll-Down-Memory-Lane-Ti-Calculator-Episode-1/title.gif"
            title="Yahtz"
            caption="Already I'm cringing..."%}

{% include image.html
            img="/images/2019-5-14-Scroll-Down-Memory-Lane-Ti-Calculator-Episode-1/roll.gif"
            title="Rolling dice"
            caption="Yeah grayscale on an LCD that only displays black and white."%}

{% include image.html
            img="/images/2019-5-14-Scroll-Down-Memory-Lane-Ti-Calculator-Episode-1/high_scores.gif"
            title="High scores"
            caption="I couldn't even beat my own high score when playing on an emulator."%}


So yeah I'd provide more details on how the scoring works, but I can't figure out how to open 86P files.  You should be able to run it on a Ti-Calc emulator
by just grabbing the 86G file onto the program.

I figured I just do one program at a time, there's more Ti calc stuff that went unreleased. Stay tuned.