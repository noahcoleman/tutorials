---
layout: post
title: (Not so) Simple Offset Gauge
tags: fusion 360, bantam, mistake, cnc, fail, machining, aluminum
date: 2018-04-15 00:00:01 -0500
permalink: /:year/:title
thumbnail: OffsetGauge/OffsetGauge.png

---
One of the great things about the Othermill (and the newer Bantam Tools machine) is the fixturing bracket.  You screw the bracket down, the mill probes the it to know where it is, and then you can align your material precisely to the bracket.  It makes flip milling a lot easier, because you can align your material to either the left or right side of the bracket.  I really like it.  The only problem is when I want to mill all the way around the stock.  If I do that with my stock snugged up against the bracket, then I'll wind up milling into it. (Bad news for everyone involved!)  So, I got the idea that if I could offset my stock from the bracket by a known quantity, I could keep all the benefits of the bracket without accidentally crashing the mill into it.  

![Offset Gauge]({{ site.baseurl }}/assets/img/OffsetGauge/OffsetGauge.png){:class="img-responsive"}

### Modeling and CAM!
I whipped up a quick 1/2" offset gauge in Fusion 360.  I know that doing a full-width cut isn't ideal, but I've had success in the past using 2D Contour and ramping into the stock with the "Maximum Ramp Stepdown" set to the recommended depth of cut for the material, so that's what I set up.  I put a piece of 0.1" thick aluminum that I had scrounged from somewhere onto the bed and tried milling my widget.  Right away, I could tell things weren't going so well.  The end mill was pushing a burr ahead of it and the motor seemed to be flagging. "Not that big a deal," I said to myself, "this is an older end mill and it's probably just on it's last legs."  It got worse and as the motor bogged down more and more, I decided to cancel the job.  Thinking that maybe I was being too aggressive, I tried the same toolpath with lighter settings and got the same result.

### Yay Instagram, Boo Bad Aluminum!
About this time, I remembered a [post on Instagram](https://www.instagram.com/p/BhfwQn-FYoh/?taken-by=ekramer3) by Edward Kramer showing his Othermill cutting a slot with an adaptive toolpath and very different feeds and speeds than what I had been using. I had seen using the adaptive toolpath as a slotting strategy before on an [NYC CNC video](https://www.youtube.com/watch?v=4SusSMezMUw), and Edward's feeds and speeds intrigued me.  I followed his recipe pretty closely: 26000 rpm, 2600mm/min feedrate, 0.63mm optimal load, and 0.25mm stepdown.

Of course, like a good engineer, I changed two things at once, making it impossible to tell which one made a difference.  Fortunately it didn't matter because I got the _exact same result_.  Gummy milling, spindle RPM's flagging, I even broke a belt on the spindle motor!  I decided that this particular piece of mystery aluminum must've been a bad alloy for machining&mdash;into the recycling it went!

![Bad Aluminum]({{ site.baseurl }}/assets/img/OffsetGauge/BadAluminum.jpg){:class="img-responsive"}

### Almost there!
I looked around in my materials pile and found a sheet of 1/8" thick aluminum with 6061 printed on it&mdash;so at least I could eliminate the bad material and focus on my toolpaths. Having decided to go with the adaptive slotting route, I cut a small piece of the 6061 and affixed it to the spoilboard. Things were going well, but I was a little off in measuring the size and postition of my stock, so the mill was chattering pretty bad as it went on the side with more material.  It eventually got so bad I had to stop the job.  Not one to let a good failure go to waste, I tweaked some of the settings on my CAM operations and set out to try again.  (This is #5 for those of you keeping score at home.)

### Elimination Round!
At this point, I had changed CAM strategies, tools, and materials&mdash;all to no avail.  For this attempt, I decided to be more precise in both my physical and CAM setup.  I also changed workholding strategies.  I had been wanting to try the [masking tape and superglue]({{ site.baseurl }}{% post_url 2018-02-13-MTCAvsP02 %}) method for a while, and this seemed like a good opportunity.

I used some 3/4" HDPE to offset my stock from the fixturing bracket and glued it down to the masking tape covered bed.  Next, I loaded and and ran my updated gcode.  It went pretty well and I was optimistic about how this one would turn out.  My optimism was short lived. After the adaptive, I had programmed in a 2D contour to walk around the part and clean up the sidewall.  This meant that I had left about 0.5mm of radial stock so the 2D contour would have some material to take off.  I forgot, however, that Fusion 360 automatically adjusts the axial stock to leave to match the radial, so the mill was encountering a lot more material than it was planning on and boy, did it let me know it!

![Oops.]({{ site.baseurl }}/assets/img/OffsetGauge/AdaptiveFail.png){:class="img-responsive"}


It was a super quick op, though, and was over before I could even react.  I pulled the part out (did you hear that?  I actually pulled a finished part out!) and had a look.  Not bad.  It wasn't pretty, but it didn't need to be.  It just needed to be 1/2" wide.

### You Had One Job!
I figured that I might have had some bad tool deflection because of the extra material in the 2D contour, so I checked dimensions with my calipers.  I'm pretty sure tool deflection doesn't account for what I got.  0.533" on one side and 0.535" on the other.  You had one job, offset gauge.  All you had to do was be 0.5".

![Finished part!]({{ site.baseurl }}/assets/img/OffsetGauge/FinishedPart.jpg){:class="img-responsive"}

### Sixth Time's the Charm
I knew I could get better dimensional accuracy and a better surface finish, so I tried one more time.  I fixed my adaptive toolpath so it went all the way to the floor and added a second finishing pass to help deal with any tool deflection.  I did get a better result (0.513" and 0.515"), but still not within the Othermill's spec of 0.003".  I need to do some more investigating what may be affecting this, but for now, it was good enough.

![Finished part!]({{ site.baseurl }}/assets/img/OffsetGauge/Donesies.jpg){:class="img-responsive"}

### Conclusion and Takeaways
I learned a lot from this seemingly simple project:

- **Use known materials.**  Weird alloys yield weird results.
- **Adaptive slotting is awesome!**  I felt like it was about the same amount of machining time, but even if it is slightly longer, it's worth the peace of mind and the extended tool life.
- **Speeds and Feeds.**  Edward Kramer's speed and feed suggestions on Instagram were spot on: higher spindle rpm, faster feedrate, smaller cuts.
- **Masking tape and superglue for the win!**  I really liked this method.  I felt it was a lot more secure than the double sided tape I've been using.
- **Precision in setup is a good thing.**  I'm going to be much more careful in the future about setting up my stock correctly both in CAM and on the mill.
- **Every failure is an opportunity to learn.**  I had many learning opportunities on this project&mdash;i.e., I failed _a lot_.  Sometimes the most frustrating failures yield the most learning.

I hope this was instructive; I know I certainly learned a lot!  As always, hit me up on Instagram or email me with any questions, comments, or suggestions.  Links to both of those are below!
