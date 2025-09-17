---
layout: post
title:  "Building a PiDP-11"
date:   2025-08-12 16:00:00 +1000
tags:   Electronics, Learning, Programming
---

So I have been on a bit of a run reading books about the computer industry mainly through the 70's and 80's.  I started with [The Idea Factory](https://www.goodreads.com/book/show/13119596-the-idea-factory) which is all about Bell Labs, from its beginning in the 1920s until it's demise in the 1980s.  It's simply amazing to see what (and who) came out of Bell labs over that 60 year period.  I then read [Dealers of Lightning](https://www.goodreads.com/book/show/1101290.Dealers_of_Lightning) which is all about Xerox PARC from the early 70s through to the 90s.  Again seeing what (and who) came out of PARC is fascinating and the stuff of legends within the computing industry.  That then put me onto [Steve Jobs & The NeXT Big Thing](https://www.goodreads.com/book/show/20339656-steve-jobs-the-next-big-thing) which was written early to mid 90s when NeXT looked like it could still "win".  Hearing about some of Apples early success (namely with University campuses) and then how Jobs tried to replicate that but failed with NeXT, and just how much appeared to hinge on him as opposed to the product or the company was pretty interesting.  Both the previous books referenced Sun Microsystems quite a lot - so my next one was [Sunburst: The Ascent of Sun Microsystems](https://www.goodreads.com/book/show/3860925-sunburst).  Again this one was written mid 90s while Sun was still very much on the rise.  It's a fascinating look at how the company got started, changed pretty early on and then went on to be the success it was for at least a decade.  

All of these books referenced Bill Gates, Paul Allen and Microsoft.  So for that side of things I read [Source Code: My Beginnings](https://www.goodreads.com/book/show/214100921-source-code) which is about Bill Gate's early life up to the start of Microsoft (and it's first few years before it really took off).  It turns out Bill Gates intends to write three books - this one covering his early life, a second covering his time at Microsoft, and a third for his time post Microsoft.  Bill Gates talked a lot about Paul Allen, so I read [Idea Man: A Memoir by the Co-found of Microsoft](https://www.goodreads.com/book/show/11698456-idea-man).  This one was written right around the time Microsoft was still doing phones and Paul Allen thought Microsoft might be able to turn that around.  Paul Allen played a critical role very early in the piece for Microsoft with his emulator - but I didn't realise he left so early.  He then did a huge number of random things with the excessive wealth that his time at Microsoft granted him for the remainder of his life.  Lastly I read [Show Stopper!: The Breakneack Race to Create Windows NT and the Next Generation at Microsoft](https://www.goodreads.com/book/show/1416925.Show_Stopper_).  This is a pretty crazy read about the absolute crunch at Microsoft to deliver Windows NT.  David Cutler is still at Microsoft today (2025) at the time of writing - and has gone on to do a number of big things there.

Reading the same stories from different perspecitves I found exceptionally entertaining and thought provoking.  It also REALLY made me want to play with some of the computing devices of the period, like the [IMSAI 8080](https://en.wikipedia.org/wiki/IMSAI_8080), and the [PDP-11](https://en.wikipedia.org/wiki/PDP-11).  Original hardware is very expensive (if you can even find it) - however there are a number of people now producing replica hardware based around things like Raspberry Pi's.  Enter the [PiDP-11](https://obsolescence.wixsite.com/obsolescence/pidp-11) from Obsolescence. These guys make AMAZING kits and are well worth checking out if this is your jam.  I ordered a PiDP-11 and spent a day putting it together.

While I waited for the kit to show up - I got a RaspberryPi 4 setup and installed with the PiDP11 emulator:  

![Building a PiDP11 1](/images/Building a PiDP11 1.jpg)

Once installed and configured you can just SSH in over wireless and it drops you straight into a screen session in the PDP 11 emulator:

![Building a PiDP11 2](/images/Building a PiDP11 2.jpg)

The kit arrived and I unboxed it ready for a day of soldering:

![Building a PiDP11 3](/images/Building a PiDP11 3.jpg)

![Building a PiDP11 4](/images/Building a PiDP11 4.jpg)

The [build instructions](https://obsolescence.wixsite.com/obsolescence/pidp-11-building-instructions) are amazingly detailed, and there is also a [YouTube series](https://youtube.com/playlist?list=PLrmxUptw9PkFTOzVk_7VM1_PLqkl-rbjr&si=4UP3PkUBwbWrmHu6) to follow if you prefer that format too.  So much thought has been put into the kit, the quality of the parts and how to assemble it.  I followed along, installed all the base components and then the LEDs - for which they give you a second PCB that sits on the LEDs to make sure they are all aligned:

![Building a PiDP11 5](/images/Building a PiDP11 5.jpg)

![Building a PiDP11 6](/images/Building a PiDP11 6.jpg)

At this point I wanted to make sure everything was working as expected before starting on the switches.  Here's a video after the first power on (with the RaspberryPi on the back running the emulator):

<p><video width="640" height="360" preload controls><source src="/videos/Building a PiDP11 1.mp4" type="video/mp4"></video></p>

With that working it was time to move onto the switches.  Again you are given extra PCBs to use to help keep all of the switches aligned while soldering (along with some cable ties).  Unlike the LED PCB though this one comes off once you are done.  These switches are repllicas that have been built for this kit (and are amazing).  However you do need to be careful you don't put too much heat into them when soldering:

![Building a PiDP11 7](/images/Building a PiDP11 7.jpg)

![Building a PiDP11 8](/images/Building a PiDP11 8.jpg)

![Building a PiDP11 9](/images/Building a PiDP11 9.jpg)

With the switches done, I installed the Raspberry Pi on the back again for the last time:

![Building a PiDP11 10](/images/Building a PiDP11 10.jpg)

I then mounted the board in the case (which again is amazing quality - picking up the theme here) and turned it on for another self test (it takes about 15 seconds to boot before you'll see the LEDs come on):

<p><video width="640" height="360" preload controls><source src="/videos/Building a PiDP11 2.mp4" type="video/mp4"></video></p>

Everything worked!  I went through the test mode with all of the switches and they all worked first go!  I'll now spend some time getting to know the software side of this thing - it's so freaking cool!