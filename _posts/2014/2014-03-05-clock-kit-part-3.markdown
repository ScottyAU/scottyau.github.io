---
layout: post
title:  "Clock kit Part 3"
date:   2014-03-05 19:25:00 +1000
tags:   Clocks, Electronics
---

So after the last post, I ordered a USB-FTDI adapter and some appropriate jumper cables so I could reprogram the STC12C5620AD.  They took about a week to show up - which brings me to this post.

First thing was to solder on a 4 pin header to the clock.  The 4 pins are marked pretty clearly as the ISP header between the hour and minute displays.

With that set to one side, it was time to setup the laptop to program this guy.  I first installed the FTDI driver package from the FTDI site.  I then plugged in the FTDI adapter to find that it wouldn't recognise properly.  I tried unplugging and plugging it back in a few times, as well as different USB ports to no avail.  I then decided to try a different mini usb cable I had and voila - it worked first go.  With the board recognised I had my new serial port to talk to the STC chip on.

Next step was to find the software to program this guy.  Thankfully STC now provide an english version of the ISP software.  It's available here.  This is just a standalone executable you run.

The software while not terribly user friendly, only requires a couple of settings.  Open it up, set the "MCU Type" (in this case STC12C5620AD) and the comm port that was setup when the FTDI adapter was installed.

It is important to note that to talk to the MCU with this ISP software, you need to start whatever action you desire in the software and then power on the MCU.  This MCU expects data on the RX when booting to action commands from the software.

So the way I did it was to first plug in all 4 jumper leads (VCC, GND, RX, TX).  With all 4 plugged in the clock should work as normal (thanks to the 5v supplied by the FTDI adapter).  If this is the case then unplug the GND jumper cable at one end.

In the ISP software now hit the "Check MCU" button, and the software should say waiting.  Then plug the GND jumper back in and you should see some info about the MCU type and F/W version show up like this:

![LED Clock Pt3 1](/images/LED Clock Part 3 1.png)

If when you plug in the GND jumper you don't get the above and the software still says waiting, switch the RX and TX cables over and try again.

Now that i'd confirmed I could talk to the MCU, I planned to write the existing code I had received from the seller.  My expectation being that the behaviour of the clock would not change.

I received the source from the seller, and after setting up Keil with the header files required for this MCU, I tried to compile the source to the required HEX file.  I was caught out though, as the free version of Keil has some limitations on the amount of compile byte code it will generate - limitations that meant I couldn't compile the source for the clock.  I did email the Keil guys about purchasing the software, but unfortunately they don't offer a hobby type licence.  The retail cost was a little more than I could afford.

I started looking around at some open source alternatives, like SDCC.  While looking around I went back to the bundle of files I had been sent by the seller and noticed that there was already a HEX file there that looked about the right size.  

I figured this was the code that had been flashed to the MCU before sending it out, so thought i'd try flashing it.  This would allow me to confirm the flashing procedure worked with the clock behaviour expected to remain unchanged.

So to do this, hit the "Open Code File" button and select the HEX file you wish to flash.  Make sure the GND jumper is disconnected again and now hit the "Download/Program" button.  The software should say waiting, now plug in the GND jumper again.

You should see MCU being programmed and when finished you should see "Complete !" like this:

![LED Clock Pt3 2](/images/LED Clock Part 3 2.png)

So I'd successfully flashed the HEX file I had, and this is what the clock looked like:

![LED Clock Pt3 3](/images/LED Clock Part 3 3.jpg)

That looks strangely correct to me.  So I power cycled the clock to confirm and sure as anything - IT WORKED!!!  It would appear that the seller did have the correct version of the code for this clock compiled - but hadn't flashed that version to the MCU.  

I spent a little bit of time figuring out how to set the time with the remote.  Hit the "mute" key to put it in programming mode and a section will flash (hour/minute/seconds).  Set the value using the numbers on the remote.  Use the "skip track" keys to move between sections (hour/minute/seconds) to set each section.  Once complete hit the "play/pause" button to confirm.

I then put the battery in, and put the case on:

![LED Clock Pt3 4](/images/LED Clock Part 3 4.jpg)

Pretty stocked with the outcome.  Nice learning exercise and good practice in SMD soldering, and a little bit of flashing a MCU.  Time for the next project.