---
layout: post
title: Custom LED Marquee Letter PCB
tags: fritzing, pcb, svg, illustrator, electronics, CNC, tutorial,
date:   2018-11-16 13:52:26 -0500
permalink: /:year/:title
---

I have an electronics project I am working on and I need to cut out a PCB on my [Bantam Tools CNC Mill](www.bantamtools.com).  Unlike other projects, however, where a regular ol' square PCB will do, this one really needs a custom shape, since I'm making LED marquee letters.

I'm using Fritzing to design the circuit, but I've never made a custom shaped board before.  In theory, it's as simple as creating an SVG with your shape and importing that into Fritzing, but in practice, it is not so straightforward.  I had a few bumps along the way, so hopefully you can benefit from my struggle.

For this tutorial, you will need:
- Adobe Illustrator
- [Fritzing](www.fritzing.org)
- A text editor, like [Atom](www.atom.io)

### A Few Helpful Links
I suggest you familiarize yourself with these pages before continuing here.  
- [How to make a custom PCB shape.](http://fritzing.org/pcb-custom-shape/)
- [Fritzing forum thread on problems with cutouts.](http://fritzing.org/forum/thread/3395/)

### Adobe Illustrator
I'm using Illustrator because I'm more familiar with it, but you could also use [Inkscape](www.inkscape.org).  If you do use Inkscape, some of the steps will be different, but this is still possible to do.

First, open up a new file and then create your artwork.  My project is going to have letter-shaped PCBs, so I used the text tool to get a letter in the font that I want, then went to `Type > Create Outlines` to convert it to vectors.  I also added a little rectangle at the bottom to make sure it sits flat.
Some of the letters, like "B," have closed loops, so there will be cutouts in those boards.  **Fritzing should handle these just fine (MAKE SURE THIS IS TRUE)**  So if you need cutouts in your board, wether it is functional or just for looks, this process will work the same.

Make sure, per the Fritzing tutorial, that you create a "board" sub-layer and "silkscreen" sub-layer.

#### Save As...SVG
This one took me some time to figure out.  The best way to get this thing out as an SVG is to go to `File>SaveAs...` and select `SVG`, then `Tiny SVG 1.2`.

### Edit SVG Manually
I'm not 100% sure why Fritzing can't handle an SVG straight out of Illustrator, but that's the way life is sometimes, so I had to manually edit the SVG in a text editor.  Luckily, Clacker, a user on the Fritzing forum, shared the [necessary edit](http://fritzing.org/forum/thread/3395/):

```
Open your file in a text editor.  In the svg section at the top you'll see:

x="0px" y="0px"

Replace that with

width="100%" height="100%"

save, and it loads in Fritzing.
```

### Import into Fritzing
Now, open up Fritzing and go to the PCB tab.  Select the PCB and click *"load image file"* in the Inspector.  
(PHOTO)

Navigate to where you saved your SVG file and it should show up just as it was in Illustrator.  You can now populate your design with parts and traces!
