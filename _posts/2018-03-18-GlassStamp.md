---
layout: post
title: CNC Milled Glass Stamp
tags: glass, cnc, glassblowing, brass, metal, fusion 360, adaptive, feeds and speeds, fixturing
date: 2018-3-18
permalink: /:year/:title
thumbnail: Prunt/finalPrunt.JPG
---

Part of my day job involves managing the glassblowing studio at [Ringling College of Art & Design](www.ringling.edu) and I have been wanting to make something for the hot shop with my CNC.  After some thought and a little research, I settled on making some hot glass stamps.  I found out they're called [prunts](https://en.wikipedia.org/wiki/Prunt) and they're usually used to stamp designs into blobs of hot glass that have been applied to a vessel or other object.

![Raspberry designs stamped onto a vessel.]({{ site.baseurl }}/assets/img/Prunt/pruntExample.jpg){:class="img-responsive"}

#### Design
I wanted to start out by making a traditional prunt design, so I chose a raspberry motif like the one shown above.  I saw a lot of these in my research, and it also seemed pretty simple to make from a modeling standpoint.  I modeled up the design in [Fusion 360](https://www.autodesk.com/products/fusion-360/overview), by creating a pattern of overlapping spheres cut out of the top of a cylinder.  As a part of the overall design, I'm going to attach the prunt to a handle with a bit of threaded rod.  Additionally, I can use the threaded hole for holding the stock in the mill.

#### Preparing My Stock
I cut off some hunks of 1/2" diameter 360 brass that I got at the local metal supplier.  Despite my best efforts, they didn't come out square.  Before milling them, I needed at least one face square to the rod's length.  If I had a metal lathe, that would've been a super easy operation, but I don't have one (yet).  I figured that if I could get close to having a flat face, I could face the other side on the mill, flip it, and then face it again and have parallel, _mostly_ square faces.  I do have access to a wood lathe, so I chucked up my blank and tried to do a quick-n-dirty facing operation.  Surprisingly, it worked!  While I was at the lathe, I also put a dimple in the face to mark the center for drilling later.

!["Facing" on the wood lathe.]({{ site.baseurl }}/assets/img/Prunt/lathe.JPG){:class="img-responsive"}

Back at the CNC mill, I put the lathed side down and and held it in place with a generous bead of hot glue around the base.  Once I had faced the top, I flipped it and re-faced the bottom.  With two fresh, clean, parallel faces, I drilled and tapped a hole in the side I had dimpled earlier.

![Freshly faced.]({{ site.baseurl }}/assets/img/Prunt/facing.JPG){:class="img-responsive"}

#### Workholding
Since I plan on attaching the prunt to a handle with a length of threaded rod, I decided to use the threaded hole on the back for workholding as well.  I created a fixture for this using some 1/4" aluminum and mounted the blank to the fixture with a flathead screw.  I needed to add a few washers underneath the stock because I didn't have a shorter screw.  I then bolted the whole thing to the T-slot bed of my [Bantam Tools](www.bantamtools.com) mill.

![All buckled in and ready to go.]({{ site.baseurl }}/assets/img/Prunt/workholdingSetup.JPG){:class="img-responsive"}

#### Software Setup
![Screenshot]({{ site.baseurl }}/assets/img/Prunt/softwareScreenshot.png){:class="img-responsive"}

Setting up the fixture in the control program was a bit of a challenge.  In the Bantam Tools software, it is only possible to set up stock in reference to the spoilboard or the fixturing bracket.  Because I'm using neither of these in my setup, I had to calculate the stock location _as if the spoilboard was there_.  It's just some arithmetic, but it would be handy to be able to set an arbitrary origin.  Also, for some reason that I still have not figured out, my math for the X axis would not add up, so I had to eyeball it.  Had this been a job that needed more precision, I'm not sure what I would need to do to calculate the stock position.

#### CAM
I used an adaptive clearing tool path with a 1/8" ball mill to remove the bulk of the material, leaving 0.1mm of radial and axial stock.  Following that was a spiral tool path for finishing using a 1/16" ball mill.  Total machining time was less than ten minutes&mdash;which felt a little silly after all the preparation I had done&mdash;but hey, that's machining in a nutshell.

I'll probably do a longer post on this further down the road, but I've been experimenting with doing full-depth adaptive tool paths in Fusion 360 and having a lot of success.  The [feed and speed recommendations](https://support.bantamtools.com/hc/en-us/sections/115000212374-Materials) provided on the Bantam tools website don't get into ideal tool engagement for full-depth cutting, they just give a standard depth of cut.  I'd like to treat that more fully in a future post.

#### Milling and Finishing Touches
Like I said, this job took less than ten minutes and it was done.  Though the feeds and speeds from [my tool libraries]({{ site.baseurl }}{% post_url 2018-1-28-Fusion360ToolLibraries %}) were technically successful, they were also a uncomfortably aggressive.  I wish I had turned it down a notch and gone with a slower feed rate.  Nevertheless, I was super impressed and happy with how it turned out!

![Almost there!]({{ site.baseurl }}/assets/img/Prunt/finishedMilling.JPG){:class="img-responsive"}

I gave the brass a quick scrub with a Scotchbrite pad, turned a handle out of a piece of cherry from the scrap bin, and assembled the prunt.  I'm not gonna lie, I think it looks fantastic and I can't wait to stamp raspberries all over some hot glass.  I have a few ideas for other, less traditional, prunt designs that I'm going to make, and I feel like I've got a good idea what to expect and how to improve that process when I do.

![Finished.]({{ site.baseurl }}/assets/img/Prunt/finalPrunt.JPG){:class="img-responsive"}

As always, thanks for reading and please contact me below if you have any questions or comments.
