---
layout: post
title:  "Mini 7-Segment Clock (times two)"
date:   2014-05-10 22:34:00 +1000
tags:   Electronics, Programming, Clocks
---

I follow quite a few electronics type blogs now, they're a great way to learn new things and see what other people are making.  One particular blog that I've been following for quite some time is [Kevin Rye](http://kevinrye.net/).  If you haven't checked out his blog before go get a coke and sit down and have a read.

He [announced](http://kevinrye.net/files/mini_7_segment_clock_kit_for_sale.php) last month that he was selling a limited run of kits of the latest version of his Mini 7-Segment Clock - so I ordered two.  Not only are the clocks awesome, but it would be a great chance to do some more SMD work, I get to burn a bootloader to an ATMega and program it with the FTDI usb-serial adapter I recently got.

They arrived this week and I sat down this afternoon to put them together.  I just followed along the blog post and assembled them both in that order:

![Mini 7 Segment Clock 1](/images/Mini 7 Segment Clock 1.jpg)

![Mini 7 Segment Clock 2](/images/Mini 7 Segment Clock 2.jpg)

![Mini 7 Segment Clock 3](/images/Mini 7 Segment Clock 3.jpg)

I made up the cable to burn the boot loader using my Arduino Uno and then used my FTDI adapter to upload the sketch:

![Mini 7 Segment Clock 4](/images/Mini 7 Segment Clock 4.jpg)

One worked first go, the second one had the same segment of each digit in the display that didn't work.  Thanks to the Eagle files for the clock if was a very quick process to fix.  I first checked the resistor which was fine, so then checking the pin on the ATMega showing it was at fault.  A touch up with the iron and the second clock was working 100%.

I then changed the sketch to display 24 hour time instead of 12 hour time  - a personal preference.  With them both working completely it was time to look at powering them.  I had 2 very cheap knock-off Apple lightning cables ($3 each) that both failed (I note if you buy the kits now they come with a USB power cable).  So I cut them up and used them, and put them both in their cases:

![Mini 7 Segment Clock 5](/images/Mini 7 Segment Clock 5.jpg)

Pretty stoked with them - and I throughly enjoyed the process of putting them together.   Now I just have to work out where I want to put them...