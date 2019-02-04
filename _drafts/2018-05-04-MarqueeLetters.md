---
layout: post
title: Marquee Letter PCBs
tags: bantam, othermill, leds, electronics, pcb, custom pcb, light, gift
date: 2018-05-04 8:00:01 -0500
permalink: /:year/:title
thumbnail: MarqueeLetters/ThumbnailImage.jpg
---
Sometimes I'm crafty (not like _sly_ crafty, more like _arty_ crafty), and this post is about one of my crafty projects.  I decided to make some old-timey looking marquee letters on my [Othermill](www.bantamtools.com) with LEDs instead of incandescent bulbs. To get a similar look, I'm using 10mm warm white LEDs.  The warm white will give off a more yellow light&mdash;similar to a tungsten bulb&mdash;and the 10mm LEDs are nice and big.  Of course, you could use use regular 5mm or 3mm LEDs (they're usually cheaper and more readily available) or make the letters smaller to keep the same proportions.  Marquee letter brooch anyone?

### Design in Fritzing
I used Adobe Illustrator to [make custom board shapes]({{ site.baseurl }}{% post_url 2018-04-20-CustomShapePCBFritzing %}) and imported them into [Fritzing](www.fritzing.org).  If you aren't familiar with Frizting, it's an open-source program that makes designing circuits pretty accessible.  You can design a circuit on a virtual breadboard, as a schematic drawing, as a printed circuit board (PCB), or all three.  The PCB design can be exported as an image or as Gerber file&mdash;an industry standard for PCB manufacturing.  This means that a board designed in Fritzing can be sent to a board house to be mass-produced (or it can be sent to the Bantam Tools software to be milled out.) I first learned how to design PCBs in Fritzing, and its still my go-to for simple circuit designs because it's so quick and easy to use.

The circuit is relatively simple: a couple of power connections, a few LEDs, and some resistors.  On both the letters, I put power pins on both the left and right, so you could daisy chain them together if you want.  Once I had all the components placed on the board, it was time to route everything.  This is usually the part that takes the longest.  Because traces between parts cannot cross one another, you might need to use some creative routing strategies to get everything connected.  

I decided to use a [ground plane](https://en.wikipedia.org/wiki/Ground_plane) to connect all of the&mdash;you guessed it&mdash;ground connections on my board.  This saved a little time figuring out the routing, but I probably spent just as much time double-checking that components with a ground connection were all touching the ground plane and weren't cut off by a trace. To use a ground plane in Fritzing, you need to first select "ground seeds," that is, to designate which pads should be connected to the ground plane.  To do this, right-click on the pad you wish to connect to ground and check the box that says "create ground seed." Do this for all ground connections, and go to `Routing > Ground Fill > Ground Fill (top and bottom)`.  After a bit of calculation, the empty space on your board will be filled with copper and the pads you designated as ground seeds should be connected to the ground plane with little tabs.

_**Note:**_ If you move a trace or component, you will need to generate the ground fill again. You can also remove all the ground fill areas by going to `Routing > Ground Fill > Remove Copper Fill`.  This usually makes it easier to see the other connections.

Once I had my components and traces right where I wanted them, I generated the ground plane one last time and exported the Gerber file for my board.  To do this, go to `File > Export > for Production > Extended Gerber (RS-274X)` and select a location for the Gerber files.  This will export multiple files for different aspects of the board, so I like to make a folder just for the Gerber files so things stay nice and tidy.

### To the Bantam mill!



### Additional Resources
- [Fritzing documentation.](www.fritzing.org/docs)
- [Bantam Tools tutorial on exporting Gerber files from Fritzing.](https://support.bantamtools.com/hc/en-us/articles/115001687554-Fritzing)
-  
