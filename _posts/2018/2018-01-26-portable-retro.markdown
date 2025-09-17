---
layout: post
title:  "Portable retro!"
date:   2018-01-26 19:57:00 +1000
tags:   Electronics, Retro Computers, Repair
---

So I have always loved small portable electronics - and retro is no exception.  There is a portable retro machine I have always love the look of - so about six months ago I started searching for one that wasn't going to require me to take a loan.  I found one that was listed as non-working/parts only but great cosmetic condition, going cheap and so I took a punt:

![Portable retro 1](/images/Portable retro 1.jpg)

The computer that Bill Gates himself last wrote software for, the Radio Shack TRS-80 Model 100:

![Portable retro 2](/images/Portable retro 2.jpg)

It showed no sign of anything when given power and turned on - as stated in the ad.  I left it plugged in for a while, as all the documentation around this guy says the internal battery needs a decent charge for the display to function 100%.  This didn't make a different though (not surprising when you see below).  This thing was cosmetically almost perfect.  No yellowing or scratches - that's a good start.  Better yet it came with this guy:

![Portable retro 3](/images/Portable retro 3.jpg)

A "SuperROM" expansion rom (more on this in a future blog post).  Unfortunately this is were the good news finishes.  I opened it up to see what I was dealing with:

![Portable retro 4](/images/Portable retro 4.jpg)

I was greeted with a pretty acidic smell and corrosion pretty much everywhere!  I haven't seen something this bad in person before.  Take a look at the ribbon cable connector for the LCD:

![Portable retro 5](/images/Portable retro 5.jpg)

![Portable retro 6](/images/Portable retro 6.jpg)

![Portable retro 7](/images/Portable retro 7.jpg)

![Portable retro 8](/images/Portable retro 8.jpg)

Most of the electrolytic capacitors had let go too:

![Portable retro 9](/images/Portable retro 9.jpg)

I removed all of capacitors that had let go:

![Portable retro 10](/images/Portable retro 10.jpg)

![Portable retro 11](/images/Portable retro 11.jpg)

![Portable retro 12](/images/Portable retro 12.jpg)

![Portable retro 13](/images/Portable retro 13.jpg)

I then cleaned up the board as best I could:

![Portable retro 14](/images/Portable retro 14.jpg)

![Portable retro 15](/images/Portable retro 15.jpg)

And replaced all of the capacitors.  Unfortunately it made no difference.  No sign of life on the display.  I used the troubleshooting guide (and stopped taking pictures - sorry!), which said start with metering the various voltages put out by the power supply.  None of these were right!  I cheated and instead of trying to diagnose any supply issues, I used my bench supply to provide the various required voltages - unfortunately this too made no difference either.  Every different output i tried to measure, from just checking voltages supplied to chips, to reset lines, data lines and everything in between.  Nothing.

This was just before Christmas.  I left all of this to sit on the bench for a bit while I enjoyed some time with family and friends away from screens of any sort.  At the start of January I had another crack at the board - but couldn't get it to show any signs of life anywhere.  So while I continued to play, I kept looking online to see if I could find another unit that might have a better chance of being brought back to life.  I was lucky enough to find exactly what I was looking for - a unit in "average" cosmetic condition, but in working condition going for a lot less than these things commonly go for - and so I bought it.

This is the first time I have "given up" and not been able to fix something.  This annoyed me a little - but is also a risk you take buying 30+ year old electronics online.  I waited for the second unit to arrive, and got straight to work when it did:

![Portable retro 16](/images/Portable retro 16.jpg)

It was quite yellow (more so than shows in the picture above), it had a rattle when I moved it and it also wasn't screwed shut.  However - it worked!  The display wasn't great but I could see what I was supposed to when I powered this guy up - thats a good start!  I took a breath and opened it up to see what this unit might hold.  I wasn't super excited when I took the four case screws out and one of the four was obviously a replacement - and a poor one at that:

![Portable retro 17](/images/Portable retro 17.jpg)

The board looked pretty good (I guess anything wold compared to the last unit):

![Portable retro 18](/images/Portable retro 18.jpg)

I then discovered what the rattle was, and why the case didn't seem to be screwed shut despite having all four case screws done up tight - two of the stand offs on the bottom of the top half of the case had snapped off and were rolling around inside the case (bottom two corners):

![Portable retro 19](/images/Portable retro 19.jpg)

This is what I found rolling around inside:

![Portable retro 20](/images/Portable retro 20.jpg)

Looking around for signs of corrosion I didn't see much at all.  The battery looked like it had just started to let go - lucky!  So out it came:

![Portable retro 21](/images/Portable retro 21.jpg)

![Portable retro 22](/images/Portable retro 22.jpg)

There was a small amount of corrosion on the board - but nothing that didn't clean right off with some isopropyl alcohol:

![Portable retro 23](/images/Portable retro 23.jpg)

I put a new battery in, and then had a look at the capacitors.  I couldn't see much - but thought for the small cost of recapping why not rip them out - I'm glad I did:

![Portable retro 24](/images/Portable retro 24.jpg)

![Portable retro 25](/images/Portable retro 25.jpg)

Most of the ones I pulled out showed signs of letting go like those above.  Again I think i got super lucky and caught these ones just in time!  There are a couple of larger capacitors I didn't have replacements for - so I will come back and replace them in the near future.  From here I decided to take a look around the board more generally.  The DB25 RS232 port on this guy was pretty gross - I don't know what the previous owner had done to it.  The installed RAM expansions also stood out a little:

![Portable retro 26](/images/Portable retro 26.jpg)

So since I now have a spare - I thought why not switch them out?  So that's what I did.  I removed the DB25 and soldered RAM from the non-working unit:

![Portable retro 27](/images/Portable retro 27.jpg)

![Portable retro 28](/images/Portable retro 28.jpg)

![Portable retro 29](/images/Portable retro 29.jpg)

I had to remove the DB25 from the working unit, the RAM expansions though are socketed - so just needed to be removed (no de-soldering required).  Once that was done I installed the replacement parts and put the board back in the case from the non-working unit (that was in fantastic condition):

![Portable retro 30](/images/Portable retro 30.jpg)

![Portable retro 31](/images/Portable retro 31.jpg)

I swapped the LCD from the working unit into the non-working units case (given the corrosion you saw on the connector alone above) and took the keyboard out and gave it a good once over.  At that point I put the whole thing together.  Low and behold - my new working 32K TRS-80 Model 100 computer:

![Portable retro 32](/images/Portable retro 32.jpg)

I've got a few things to try with this guy now that it's working - but that will be the topic of another blog post some time soon I hope.