---
layout: post
title: Custom PCB Shape in Fritzing using Adobe Illustrator
tags: fritzing, pcb, svg, illustrator, electronics,  
date:   2018-11-16 13:52:26 -0500

---
{{page.title}}

I have a new, secret project I am working on.  It's an electronics project and I'm going to need to cut out a PCB on the [Othermill](www.othermachine.co).  Unlike other projects, however, where a regular ol' square PCB will do, this one really needs a custom shape.  I decided to design it in Fritzing, since that's the program I'm most comfortable with, but I've never made a custom shaped board before.  In theory, it's as simple as creating an SVG with your shape and importing that into Fritzing, but in practice, it was not so straightforward.  I had a few bumps along the way, and I want to share those so it is easier for those following in my footsteps.

For this tutorial, you will need:
- Adobe Illustrator
- Fritzing
- A text editor, like [Atom](www.atom.io)

### A Few Helpful Links
- [How to make a custom PCB shape.](http://fritzing.org/pcb-custom-shape/)
- [Fritzing forum thread on problems with cutouts.](http://fritzing.org/forum/thread/3395/)

### Adobe Illustrator
I know that a lot of people use Inkscape for vector work, but I happen to have access to Illustrator, so that's what I'm going to use.  First, open up a new file and then create your artwork.  My project involves some letter-shaped PCBs, so I used the text tool to create my letter, converted it to outlines, and then added a little rectangle at the bottom.  Your shape can be whatever you want.  It can even have cutouts like mine: (SCREENSHOT OF CUTOUT)

Make sure, per the Fritzing tutorial, that you have the "board" sub-layer and "silkscreen" sub-layer.

### Save As...SVG
This one took me some time to figure out.  The best way to get this thing out as an SVG is to go to 'File>SaveAs...' and select 'SVG'. Tiny SVG 1.2

### Edit SVG Manually
I'm not 100% sure why Fritzing can't handle an SVG straight out of Illustrator, but that's the way life is sometimes, so we need to edit the SVG in a text editor.  Luckily, Clacker, a user on the Fritzing forum, shared the [necessary edit](http://fritzing.org/forum/thread/3395/):

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

Navigate to where you saved your SVG file and...hopefully it works!

### If it didn't work...


<!-- Explanatory text goes here. -->
