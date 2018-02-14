---
layout: post
title: Motorcycle Cruise Control
tags: cnc, plastic, fusion 360, hdpe, motorcycle, bantam, mistake
date: 2018-2-13
permalink: /:year/:title

---
PHOTO OF MOTORCYCLE

I recently bought a 2002 Honda Shadow VLX.  I did this because **(1)** I needed a vehicle in my new, public transitless town, **(2)** said town has above-freezing temperatures year-round, and **(3)** because I've always wanted a motorcycle.  Needless to say, I've had a lot of fun tooling around on my hog.  I recently went on a longish (1.5 hours one way) trip and I wanted to be able to rest my throttle hand occasionally along the way. I had heard of throttle locks and a quick search on the Google yielded hundreds of results, most of which had a similar design: a bar that grips the throttle and gets pinned against the brake lever, thus holding the throttle in place.  I even found a few on [Thingiverse](https://www.thingiverse.com/search?q=throttle+lock&sa=&dwh=25a8228337cfb4).  This was such a simple design, I was sure I could make one on my [Bantam Tools CNC Machine](www.bantamtools.com).  

#### Design
I sketched up three or four waaaay overcomplicated and overengineered designs before I settled on this one:

PICTURE

I took inspiration from (read: copied) the photos I saw whilst googling.  In my research, I also read that this throttle lock design can be difficult to position with one hand, so I added a thumb tab to make adjusting a little easier.  With everything modeled out, I went to CAM.  Using the [HDPE tool library I created]({{ site.baseurl }}{% post_url 2018-1-28-Fusion360ToolLibraries %}) last month, I set up a simple 2D Contour operation and posted it out.

#### The First Cut is the Deepest
I added the spoil board when I set up my mill, but forgot to re-locate my tool.  The first cut ended with a terrible crunching sound as the machine sent the end mill into the spoil board it didn't think was there. Luckily, I had fast reflexes and the end mill wasn't damaged. Lesson learned: any time the spoil board height changes, re-locate the tool.

#### Take 2
Once I had recovered emotionally, zeroed the machine, and located the tool, I ran the job again and five minutes later I had an ok-looking throttle lock.  I don't think the plastic I used was actually HDPE.  I honestly don't know what it was, since I got it out of an unlabeled scrap pile.  It had a similar density, but left quite a bit of stringies on the top edge of the cut. On the plus side, the profile totally looks like a chili pepper!

PHOTO of Chili pepper

A little work with some sandpaper and a craft knife took care of the stringing and I took my creation out to the bike for a test fit.

PICTURE OF LOCK ON HANDLEBAR

This never happens, but I got the fit right on the first try!  The diamond is just a little smaller than the handlebar and the natural flex of the material holds it tight enough to lock the throttle, but not so tight I couldn't disengage it when I needed to.

#### Files
I've included a link to the file below.  You can download it as an .stl for 3D printing or as a Fusion 360 file if you want to customize it

- STL model
- Fusion 360 File
