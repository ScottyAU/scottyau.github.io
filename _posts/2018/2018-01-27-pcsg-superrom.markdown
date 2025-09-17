---
layout: post
title:  "PCSG SuperROM"
date:   2018-01-27 16:16:00 +1000
tags:   Electronics, Retro Computers
---

As mentioned briefly in my last post - I ended up with  Portable Computer Support Group (PCSG) SuperROM.  This guy is a ROM addon for the Model 100 that includes four additional applications:

 - Lucid
 - Write Rom
 - Thought
 - Lucid Data

I found the [scanned manual](ftp://ftp.whtech.com/club100/doc/sr-contents-and-overview.pdf) for this guy where I have found most of the scanned manuals I need - the [Club 100 Library page](http://www.club100.org/library/libdoc.html).  It's a pretty basic install and setup.  Power the 100 off (not the memory power switch - just the main switch), flip the device over and open the expansion bay:

![PCSG SuperROM 1](/images/PCSG SuperROM 1.jpg)

The top is the system bus, the bottom is the expansion ROM slot where the SuperROM goes - simply push it in:

![PCSG SuperROM 2](/images/PCSG SuperROM 2.jpg)

From there flip the unit back over and power it on.  At this stage you shouldn't see any difference in the display - it should just be the menu you are used to:

![PCSG SuperROM 3](/images/PCSG SuperROM 3.jpg)

If this worked you are good, if it didn't maybe try reseating the ROM and try again.  From here to tell the unit the ROM is installed, open the Basic prompt and type:

`call 63012`

This should open the SuperROM menu:

![PCSG SuperROM 4](/images/PCSG SuperROM 4.jpg)

From here you can open any of the included apps, or jump back to the main (normal) menu by hitting F8.  When you do though you will have an additional menu option "super" which will jump you back to the SuperROM menu:

![PCSG SuperROM 5](/images/PCSG SuperROM 5.jpg)

This stays there as long as the unit doesn't lose complete power (the RAM battery backup).  Pretty handy really.  I'll give the apps more of a test - but they all opened and appeared to run as they should.  #winning