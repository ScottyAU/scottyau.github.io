---
layout: post
title:  "New Bench Supply"
date:   2014-07-08 19:03:00 +1000
tags:   Electronics, Equipment
---

I finally pulled the trigger and bought a bench power supply.  Up until this point I have just been using the [ATX breakout board]({% post_url 2014/2014-03-23-atx-bench-supply %}).  I've been looking around for a while, trying to way up price vs features and finally settled on the [Siglent SPD3303D](http://www.siglent.com/en/product/detail5.aspx?id=100000014858258&nodecode=119008005).

![New Bench Supply 1](/images/New Bench Supply 1.jpg)

The supply has 2 fully adjustable channels that can work in independent, series and parallel modes.  The 3rd channel switches between 2.5v/3.3v/5v at 3A.  The display only covers the first 2 channels, the 3rd channel just has the LED displaying CV/CC mode.  The 2 adjustable channels also have a timer function which can be programmed either on the supply itself or via USB using the included software (just like other features).

I settled on this guy because it ticked all my boxes - and physically was the right size for my shelf as well.

There is quite a lengthy thread on this particular supply [here](http://www.eevblog.com/forum/testgear/siglent-spd3303d-review/) on the EEVBlog forum.  This thread mentions two issues found with the supply - namely:
Spikes / overshoots on CH3 during power on / power off of the entire supply
Spikes when the output of CH3 when a load is removed
If you read the entire thread on the EEVBlog forum you'll notice that both Siglent and the Australian supplier mention that there was a revision of the hardware late last year (2013) which fixed these issues.  As [posted by Siglent Support](http://www.eevblog.com/forum/testgear/siglent-spd3303d-review/msg467227/#msg467227) the hardware version number has not changed. The supplier confirmed that the version I had ordered was this latest revision. 

So the first thing I did was some testing when the supply showed up.  The results I got show that there is some level of fix that has been applied to the 3rd channel.  Cold start of the whole unit with a load resistor on the 3rd channel:

![New Bench Supply 2](/images/New Bench Supply 2.png)

There is still a spike there.  Removing the load from the 3rd channel:

![New Bench Supply 3](/images/New Bench Supply 3.png)

Again still a small spike.

Both of these results are less that the original issues picked up with the hardware revision from last year.  And they only occur on the 3rd channel - which I personally don't have a huge issue with.  The first two channels don't have any of these issues. 

I also wanted to note that the service I received from [TRIO Test & Measurement](http://triotest.com.au/) was awesome.  If you are in Australia check them out!