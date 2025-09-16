---
layout: post
title:  "Commodore 128 - Part 2"
date:   2014-08-13 16:30:00 +1000
tags:   Electronics, Retro Computers, Repair
---

**tl;dr** It works!  Read on for detail.

So I finally received enough bits to connect up the 128 and power it up and see if it works.  First up I needed a power supply, so I ordered one from Ray Carlsen.  Ray makes a replacement 64/128 power supply with new parts.  The design is available but as Ray mentions, sourcing all of the parts wouldn't have worked out much different to buying one from Ray.  He's a great guy who's been repairing Commodores for a long time.  Pretty impressed with the supply, and its good to know that I won't be troubleshooting any issues with the power supply side of things.  It is setup for 240v - but it still has an American plug on it.  I'm using an adapter for the moment, but once I have a setup i'm happy with i'll put an Australian plug on it:

![Commodore 128 Part 2 1](/images/Commodore 128 Part 2 1.jpg)

With the power side of things covered I needed to look to video out.  The 128 has three ports for video out, the round DIN connector, the RF connector and the DB9 connector.  The round DIN connector and RF connector display video in 40 column mode, which is what the majority of software for the Commodore 64/128 uses.  You can very easily get a cable that goes from the DIN connector to S-Video - so that's what I ordered (figuring that would be better/easier than using the RF connector and tuning in a TV):  

![Commodore 128 Part 2 2](/images/Commodore 128 Part 2 2.jpg)

The DB9 connector requires a little more circuitry to work with a modern display and outputs video in 80 column mode, for which there isn't a great deal of software.  So while that is something I intend on trying, I wanted/needed to look into it a bit more before ordering bits.  

Once I'd ordered the DIN to S-Video cable and was waiting for it to arrive I went looking at the TV I had to see how easy it would be to get a cable to it - and low and behold it does't have an S-Video input!  So I jumped back online and ordered an S-Video to VGA adapter.  I got the cheapest one I could find ($10AUD):

![Commodore 128 Part 2 3](/images/Commodore 128 Part 2 3.jpg)

So with all the parts finally in hand I plugged it all in, said a little prayer and flicked the power switch on the 128.  

Nothing.

No power light.  No smoke.  No burning smell.  No video output.  Bummer

![Commodore 128 Part 2 4](/images/Commodore 128 Part 2 4.jpg)

I'd debated taking the top off the 128 for the first power on in case something went bad but thought I'd give it a try first.  So with it failing to power on I grabbed the power cable to pull it out and as I moved it the 128 turned on!

![Commodore 128 Part 2 5](/images/Commodore 128 Part 2 5.jpg)

The video output was stable but not perfect.  I tried reseating cables and some different power supplies for the S-Video to VGA adapter but there was no difference.  Most of my googling and chatting to other Commodore users pointed at the same conclusion - the $10AUD S-Video to VGA convertor wasn't the best.  I've got a plan to get a display that will just take S-Video straight in.  Will write a blog post when I have something, showing whether the video output is any better.

So with the 128 working, one of the first things I did was "GO64":

![Commodore 128 Part 2 6](/images/Commodore 128 Part 2 6.jpg)

I then reset and typed "SYS 32800,123,45,6":

![Commodore 128 Part 2 7](/images/Commodore 128 Part 2 7.jpg)

So both the 128 and 64 modes work in 40 column mode.  As I mentioned to go 80 column I need some circuitry to use the DB9 port, and I also intend on getting  display that can take S-Video input directly.  I'll do another post on both of those when those parts arrive, which hopefully isn't too far away.
