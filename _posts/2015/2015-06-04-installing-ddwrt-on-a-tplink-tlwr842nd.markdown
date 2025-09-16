---
layout: post
title:  "Installing DD-WRT on a TP-LINK TL-WR842ND"
date:   2015-06-04 19:58:00 +1000
tags:   Electronics, Programming
---

I love playing with routers and network gear in general - who doesn't?  In the past I've never run the same router at home for long while I swap them out with different software and/or hardware.  This has slowed a bit lately due to life, but hasn't completely stopped.

I ran an early model [WRT54G](http://en.wikipedia.org/wiki/Linksys_WRT54G_series) with [DD-WRT](http://www.dd-wrt.com/) for a while a number of years ago.  That was my last foray into DD-WRT (it's been [pfsense](https://www.pfsense.org/) and now [routeros](http://www.mikrotik.com/software) since).  I wanted to give DD-WRT another go and so started looking through my box of bits to see what I might have that would work.  After a bit of digging in the parts box and reading online I soon realised most of my gear would run DD-WRT, but a 'micro' build.  I'm interested in having a play with some of the extra stuff that DD-WRT has to offer so I needed something with a little more Flash and RAM.

DD-WRT openly recommend a TP-Link [TL-WR740N](http://www.tp-link.com.au/products/details/?model=TL-WR740N) to start with, and for $19AUD from a local store it's a pretty awesome recommendation.  Getting into DD-WRT has come down in price since I last looked - which is awesome.  Looking at the supported devices list though and what else was available with a little more Flash and RAM (as well as a USB port if possible) I settled on a TP-Link [TL-WR842ND v2](http://www.tp-link.com.au/products/details/?model=TL-WR842ND) for $38AUD:

![Installing DDWRT on a TPLINK TLWR842ND 1](/images/Installing DDWRT on a TPLINK TLWR842ND 1.jpg)

This router was solely purchased to be hacked, flashed and generally tinkered with, so the first thing I did after taking it out of the box was open it up.  I know these routers have a serial header thanks to [this page](http://wiki.villagetelco.org/Serial_Port_Access_and_Firmware_Recovery_for_TL_WR842ND) (and many others) and I wanted to see if I could get a serial console first.  I found the connections, soldered on a four pin header and connected my 3.3v USB serial adapter:

![Installing DDWRT on a TPLINK TLWR842ND 2](/images/Installing DDWRT on a TPLINK TLWR842ND 2.jpg)

Once I got the pinout correct, it worked without issue (115200, 8N1).  Typing tpl when you see "Autobooting in 1 seconds" will drop you into the uboot prompt:

![Installing DDWRT on a TPLINK TLWR842ND 3](/images/Installing DDWRT on a TPLINK TLWR842ND 3.png)

Next step was to make this serial header externally accessible so I could close it back up but still access the serial console.  With a little bit of Dremel work I cut space for a 4 pin female header above the reset button on the back of the case.  I hot glued it in place and then soldered in some jumper wires.  In hindsight I probably could have removed the first header I soldered in and had the jumper wires run straight to the board, but the case has room so I left it in:

![Installing DDWRT on a TPLINK TLWR842ND 4](/images/Installing DDWRT on a TPLINK TLWR842ND 4.jpg)

I closed the case back up and got ready to flash DD-WRT with my new serial console open to watch the process, which worked without issue (serial console not required, but super extra nerd cred for having it).  I flashed the latest version at the time which was [05-27-2015-r27086](ftp://ftp.dd-wrt.com/betas//2015/05-27-2015-r27086/tplink_tl-wr842ndv2/).  I first flashed the factory-to-ddwrt.bin through the TP-Link web interface, and then flashed the tl-wr842ndv2-webflash.bin through the DD-WRT web interface.

The final step was to add a sticker to complete things:

![Installing DDWRT on a TPLINK TLWR842ND 5](/images/Installing DDWRT on a TPLINK TLWR842ND 5.jpg)

I'll need some time to get to know DD-WRT again, but I have the comfort of a serial console if things go sideways.