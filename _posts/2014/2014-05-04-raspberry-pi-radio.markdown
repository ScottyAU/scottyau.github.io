---
layout: post
title:  "Raspberry Pi Radio"
date:   2014-05-04 11:51:00 +1000
tags:   Electronics, Programming, Radio
---

I like listening to music while I work.  I stream a lot of music over the internet from places like SomaFM and Pandora.  I wanted something though that would play music for me while I work that was independent of my MacBook Pro.  Seemed like a good way to go was a Raspberry Pi with the Adafruit LCD.

I love the stuff from Adafruit.  It's always great quality and has very clear instructions and in most cases tutorials on how you might like to use some of the bits.  So I ordered my LCD kit (and some other bits) and waited.

Once the bits arrived it was a very straight forward matter of following the instructions to put the LCD shield together:

![Raspberry Pi Radio 1](/images/Raspberry Pi Radio 1.jpg)

![Raspberry Pi Radio 2](/images/Raspberry Pi Radio 2.jpg)

Pretty simple.  Once I confirmed the LCD worked as expected I moved onto the [Adafruit pi wifi radio tutorial](https://learn.adafruit.com/pi-wifi-radio).

This by and large worked - there were just two small pieces I had to change to make this work 100% for me.  The first was that the current pianobar package available through the RPi repositories is sufficiently old that it suffers from this [bug](https://github.com/PromyLOPh/pianobar/issues/321).  This is not the TLS fingerprint issue - but a separate one.

So I removed the apt installed version and downloaded and compiled pianobar from source.  Worked first go without issue.

So I moved onto adding the few lines that run Adafruits python at startup - and it only work some times.  After a little debugging it turns out sometimes my wireless connection on my RPi wasn't quite ready and so things were timing out which it why it only worked on startup sometimes - but worked 100% if I ssh'd in and started it manually.

To fix this all I did was add a sleep statement (for 5 seconds) to the startup commands and now it works first time every time!

Overall (not counting the time for the LCD to arrive) this whole thing is very straight forward and start to finish shouldn't take more than an hour or so to complete, but i'm still pretty stoked.