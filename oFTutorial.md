#openFrameworks Quick-Start Guide for Mac

This tutorial is for people who, like me, need some immediate gratification in order to feel like they are being productive.  The goal of this tutorial is for you to get openFrameworks up and running on your computer and get a basic program written that you can play around with in under an hour.  
Disclaimer:  I am still very new to openFrameworks and to coding in general.  There will probably be many errors (please let me know) and there won't be a lot of coding theory.  I will _not_ be explaining why things work the way they do.  That's what the other tutorials are for.  This is more of a step-by-step, quick-start guide.

##Steps
1. Download [Xcode](https://developer.apple.com/xcode/).
2. Download [openFrameworks](http://openframeworks.cc/download/).
3. Create your first program!
4. Let's write some code.
5. I like to move it, move it.
6. Learn more.

###Step 1: Download Xcode
You need somewhere to write your code.  An IDE (Integrated Development Environment) is a program that helps you write your code and then compile it and run it. (For more information on what compiling is and what an IDE is, check out  [this tutorial](http://openframeworks.cc/tutorials/introduction/000_introduction.html).  Apple makes a free IDE called Xcode which is quite nice.  You can find it [here](https://developer.apple.com/xcode/).

###Step 2: Download openFrameworks
Once Xcode is installed on your machine, go ahead and install the latest version of openFrameworks (this tutorial is for Mac machines, so you will want to download the version for OSX). Save it wherever you want to (I recommend in your Documents folder or something similar).

####Intermission: We need to talk about .h files and .cpp files
If you're like me, you may have dabbled in some Arduino or some Processing before stepping up to openFrameworks.  One really big difference between these is that an oF program has two files to make it run, whereas Processing or Arduino has only one.  The first is the header file or .h file.  The header contains some of the basic structure of the program.  It contains "what" the program needs to run, whereas the .cpp file contains "how" the program will do it.  Right now, you just need to know that in order to make something with openFrameworks, you need to be aware of both these files.

###Step 3: Create your first program!
Ok, so by now you should have Xcode and openFrameworks both downloaded and ready to go.  Let's make a new program, shall we?  First, go into the openFrameworks folder and find a folder named "projectGenerator_osx". In there, you will find the projectGenerator app:

Double click it and a window will open up that looks like this:

(insert screen shot here)

We need a name for our project. I called mine "myFirstSketch".  The path tells you where the project will be saved.  The addons box allows you to include any addons that you'll need for your project (we won't be needing any today).

Click "Generate Project" and all the files necessary will be created in the directory specified in the path field.  Close the project generator by hitting ⌘Q and navigate to the folder you created your project in (for me, that folder was /Users/Noah/Documents/of_v0.8.0_osx_release/apps/myApps).

Once there, double click the file `myFirstSketch.xcodeproj`. Xcode will open up and you will be able to get started.  

In the top left corner of the Xcode window, click on this box:
(image)
And change it to look like this:
(image)

###Step 4: Let's write some code...
Now, let's write us a few lines of basic code. On the left in your Xcode window, open the "myFirstSketch project folder", then open the "src" folder.  
(image)
Click on "testApp.cpp" and you will see something like this:
(image)
All of what is there are built in oF functions to help make your programming life easier.  Right now, though, we are just going to focus on 
    void testApp::setup(){
    } 
and 
	void testApp::draw(){
	}
If you have ever used Processing or Arduino, these will seem familiar to you.  The `setup` function runs once at the beginning of the program and the `draw` function runs continuously on a loop until the program is closed.  Let's make something.

We are going to set a background color for our project.  Follow my lead:

	//--------------------------------------------------------------
	void testApp::setup(){
    	ofBackground(255,255,0);
	
	}

Go ahead and hit the _Run_ button in the top left of the Xcode window (the one that looks like a Play button).

You should have a lovely yellow screen with nothing on it, like this:

(image)

Now, lets put something into that smashing yellow field.  In the draw function, write:

	//--------------------------------------------------------------
	void testApp::draw(){
    	ofSetColor(0, 0, 255);
    	ofCircle(200, 200, 20);
	
	}

Run your program, and you should have:

(image)

Cool, huh?  If yellow and blue isn't your thing (sorry, Sweden) and you would like to change the colors, that's great.  Just change the three values in `ofBackground` and `ofSetColor` to your liking.  The three numbers control the red, green, and blue values, respectively, so `(255,0,0)` will give you red, `(0,0,255)` will be blue, and so on.	

###Step 5: I like to move it, move it.
Now that you have fully customized your background and your circle, let's move the circle around a bit.  Now, there are lots and lots of ways to accomplish this, but this tutorial is focused on getting some quick results, so we are going to make the position of the circle analogous to the position of the mouse on the screen.  Easy, right?

Go back to your `draw` function and look at the line that says `ofCircle(200,200,20);`. 'ofCircle' is a function within openFrameworks that knows how to draw a circle.  It just needs to know where you, the programmer, want it and how big you want it to be.  That's what the numbers after `ofCircle` are for.  The first number is the x (horizontal) position, the second is the y (vertical) position, and the last number is the radius of the circle.  (Just for reference, the origin (where x and y meet) is at the top left corner of the window.)

All these numbers are in pixels, meaning if I have `ofCircle(100, 200, 50);`, my circle will be 100 pixels to the right of, and 200 pixels down from the top left corner of my window.  It will also have a radius of 50 pixels, with a diameter of 100 pixels.

Ok, back to moving our circle.  openFrameworks always "knows" where the mouse is, so we can tell our program to find out where the mouse is and put the circle there, too. For this, we'll use a function called `ofGetMouseX()` and `ofGetMouseY()`.  We just plug those into our `ofCircle` function like so:

	//--------------------------------------------------------------
	void testApp::draw(){
    	ofSetColor(0, 0, 255);
    	ofCircle(ofGetMouseX(), ofGetMouseY(), 20);
	
	}
Run that bad boy and bask in your awesomeness.
There you have it, a quick and dirty tutorial on how to get openFrameworks up and running on your machine.
###Step 6: Learn more.


