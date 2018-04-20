---
layout: post
title: Custom LED Marquee Letter PCB
tags: fritzing, pcb, svg, illustrator, electronics, CNC, tutorial, inkscape
date:   2018-04-20 13:52:26
permalink: /:year/:title
thumbnail: CustomShapePCBFritzing/Success.png
---

I have an electronics project I am working on and I need to cut out a PCB on my [Bantam Tools CNC Mill](www.bantamtools.com).  Unlike other projects, where a regular ol' square PCB will do, this one really needs a board in the shape of the letter B.

I'm using Fritzing to design the circuit, but I've never made a custom shaped board before.  In theory, it's as simple as creating an SVG with your shape and importing that into Fritzing, but in practice, it is not so straightforward.  I had a few bumps along the way, so hopefully you can benefit from my struggle.

For this tutorial, you will need:
- Adobe Illustrator
- [Fritzing](www.fritzing.org)
- A text editor, like [Atom](www.atom.io)

### A Few Helpful Links
I suggest you familiarize yourself with these pages before continuing here.  Take your time&mdash;I'll wait.
- [How to make a custom PCB shape.](http://fritzing.org/pcb-custom-shape/)
- [Fritzing forum thread on problems with cutouts.](http://fritzing.org/forum/thread/3395/)

Done? Great! Let's move on.
I'm using Illustrator because I'm more familiar with it, but you could also use [Inkscape](www.inkscape.org). The Frizting tutorial linked above shows how to do this with Inkscape.

### Adobe Illustrator
First, open up a new file and then create your artwork.  Since my project has a letter B shaped board, I used the text tool to get a letter in the font that I want, then went to `Type > Create Outlines` to convert it to vectors.  Some of the letters (like B) have a closed loop.  Fritzing will interpret these as cutouts, so if you need cutouts in your board&ndash;wether functional or just for looks&ndash;this process will work the same.

![Create Outlines]({{ site.baseurl }}/assets/img/CustomShapePCBFritzing/CreateOutlines.png){:class="img-responsive"}

#### Compound Paths
If you are making a board with cutouts, all of the lines for the board (including the cutout) need to be part of the same object, rather than multiple objects layered on one another.  In Illustrator, this is called a Compound Path.  To make this, draw the base board and any cutouts.  In the example below, the red rectangle will be the board and the black rectange will be the cutout.  Select all elements of the board (1) and go to `Object > Compound Path > Make` (2).  This will subtract the interior shapes from the exterior shape and create one "hollow" shape.

![Compound Path]({{ site.baseurl }}/assets/img/CustomShapePCBFritzing/CompoundPath.png){:class="img-responsive"}

Make sure, as the Fritzing tutorial says, that you create sublayers labeled "board" and "silkscreen", as shown below

![Layers]({{ site.baseurl }}/assets/img/CustomShapePCBFritzing/Layers.png){:class="img-responsive"}

### Exporting and Editing the SVG
This one took me some time to figure out, since there are multiple ways to output an SVG.  The best way I found was to go to `File > Save As...` and select `SVG`, then `SVG Tiny 1.2`.

Fritzing can't handle an SVG straight out of Illustrator.  I'm not sure why, but that's just the way life is sometimes, so I had to manually edit the SVG in a text editor.  Luckily, Clacker, a user on the Fritzing forum, shared the [necessary edit](http://fritzing.org/forum/thread/3395/):

```
Open your file in a text editor.  In the svg section at the top you'll see:

x="0px" y="0px"

Replace that with

width="100%" height="100%"

save, and it loads in Fritzing.
```

### Import into Fritzing
Now, open up Fritzing and go to the PCB tab.  Select the PCB and click `load image file` in the Inspector.  Navigate to your newly created SVG file, and click `Open`. Fritzing may give you a warning to make sure your board looks the way it should look.  Click `OK` and your custom-shaped board should be in there.  Mine got put way off to the side, so I just zoomed out until I could see the board and then zoomed back in on it.

![Success!]({{ site.baseurl }}/assets/img/CustomShapePCBFritzing/Success.png){:class="img-responsive"}


Navigate to where you saved your SVG file and it should show up just as it was in Illustrator.  You can now populate your design with parts and traces!

### Conclusion
I really like Fritzing for circuit design.  I think it is a great tool for beginners and less-technical types.  It has it's limitations, to be sure, but I love that with a little SVG know-how, unique board shapes can be easy to implement.

As always, I'd love to hear your questions, critiques, and feedback.  You can send me an email or find me on Instagram via the links below.  Have a great day!
