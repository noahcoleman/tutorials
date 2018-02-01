---
layout: page
title: Fusion 360 Tool Libraries
tags: fusion 360, bantam tools, cnc, 2018
date: 2018-1-28 13:52:26 -0500

---
When I found out that [Bantam Tools](http://www.bantamtools.com) had custom tool libraries on their website, I was super excited. I had downloaded their Fusion 360 tool library a while back, but I had been manually changing the speeds and feeds in every time I set up a milling operation. Let me tell you: that got tedious really fast, so I was looking forward to being able to select the tool based on what material I was cutting.

#### Failed Attempts

There are pages for the different [materials](https://support.bantamtools.com/hc/en-us/sections/115000212374-Materials) that the Bantam Tools Desktop PCB Milling Machine can cut. The library for each material is available as a download on it's page. I downloaded the libraries for the materials I most commonly use and started importing them into Fusion 360. When I clicked on the tool library; however, there were no tools!

After trying and failing several times to import the tool libraries with actual tools in them, I figured it was user error and contacted Bantam Tools support to see what I was doing wrong. They were very quick to respond and told me that the tool libraries I downloaded are for their software, not Fusion 360. That makes a lot of sense, because, without a way to change feeds & speeds, milling with [.svg files](https://support.bantamtools.com/hc/en-us/articles/115001668153-SVG-Files) in anything other than FR-1 would yield a lot of broken bits in short order.

A little disheartened, but undeterred, I set about to make my *own* tool libraries for Fusion 360.

#### DIY Tool Libraries

Using the [Fusion 360 tool library](https://support.bantamtools.com/hc/en-us/articles/115001671594-Fusion-360-Tool-Library) as a template, I made duplicate tool libraries for each entry on the materials page at bantamtools.com.

Here are links to download the Fusion 360 tool libraries I created:
- [ABS]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/ABS.tools)
- [Acrylic]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Acrylic.tools)
- [Aluminum]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Aluminum.tools)
- [Brass]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Brass.tools)
- [Delrin]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Delrin.tools)
- I skipped FR-1 because 99% of the time I mill FR-1 it's for a PCB and Bantam Tools does all the feeds & speeds work. Why reinvent the CNC machine?
- [HDPE]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/HDPE.tools)
- [Machinable Foam]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Machining_Foam.tools)
- [Machinable Wax]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Machining_Wax.tools)
- [Polycarbonate]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Polycarbonate.tools)
- Wood (Bantam Tools supplies two sets of feeds and speeds: one for plywood and one for hardwood)
  - [Plywood]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Plywood.tools)
  - [Hardwood]({{ site.baseurl }}/assets/downloads/Fusion360ToolLibraries/Hardwood.tools)

#### A Few Notes

There are two sets of feeds & speeds listed on each page: one more conservative and one a little more aggressive. I used the advanced feeds & speeds in my libraries, so keep that in mind if you plan to use these tool libraries. I take no responsibility for any ruined materials or damaged end mills!

There are two tools in my libraries that are not in Bantam Tools' default library: a 1/4" flat end mill and a [1/8" 90° drill mill](http://www.lakeshorecarbide.com/18drillmill2flute90deg.aspx).  Feel free to delete these tools if you don't want them in there.

#### How to Import Tool Libraries into Fusion 360

There are [lots](https://knowledge.autodesk.com/support/fusion-360/learn-explore/caas/sfdcarticles/sfdcarticles/How-to-import-a-tool-library-in-Fusion-360.html) of [tutorials](https://www.youtube.com/watch?v=NzBoMkaNBsE) on how to do this, so here's the short version:
1. Enter the CAM workspace in Fusion 360.
2. Click on *Tool Library* under the *Manage* tab.
3. Right-click on *Local* and select *Import Tool Library*.
4. Locate and open the appropriate file.

That's it!  I hope this was helpful for you and I'd love to hear any feedback you might have.
