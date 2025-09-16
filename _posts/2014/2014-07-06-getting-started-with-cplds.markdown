---
layout: post
title:  "Getting started with CPLDs"
date:   2014-07-06 20:34:00 +1000
tags:   Electronics, Programming, Learning
---

Just like playing with micros I wanted to get my hands on and play with come CPLDs so I went hunting around for some tutorials.  The one I settled on to start with was [this one](http://www.hackshed.co.uk/getting-started-with-cplds-index/).  It uses a CPLD from the Altera MAX II family.  The chip itself is not overly important but the branding on the chip is - as this is basically an exercise in learning how to use a the associated vendors software.  I found the same boards used in the tutorial [here](http://www.aliexpress.com/snapshot/6063556008.html), ordered and waited for delivery.

Once the boards turned up I opened one up and noticed that the board was not very clean.  There was a lot of extra flux and other gunk on the board.  It worked - it just wasn't clean, so I thought I'd have  go at cleaning it.

After googling around I found a lot of people using a lot of different ways of cleaning their boards.  At lot of people talked about just washing it with some warm soapy water, or even putting it through the dishwasher.  I found this completely weird, I've never thought water and electronics should mix.  Given these boards were so cheap though I thought it would be better to try it with one of these cheap dev boards and kill them than try it for the first time with something else.

So I washed it with some warm soapy water and a toothbrush, and it came up really well.  To make sure it dried out properly I thought I'd put it in the over for a minute.  The oven was off - after just having cooked lunch.  The board was in there for 5 minutes max - this being the result:

![Getting started with CPLDs 1](/images/Getting started with CPLDs 1.jpg)

The board was dry, but notice the melted power connector and power button below it!  I hooked up my bench supply and shorted the switch and the board still worked!  So I headed down to my local Jaycar store, but unfortunately they had no stock of the DC barrel jacks or the non-momentary switches in the foot print I needed.  So I headed home and got on eBay and ordered some replacements.  While a lot cheaper, I also then had to wait another couple of weeks for the bits to arrive from overseas.  In the meantime I carefully removed the broken components:

![Getting started with CPLDs 2](/images/Getting started with CPLDs 2.jpg)

The parts finally arrived (I also finally got the lamp for the bench that I'd been chasing):

![Getting started with CPLDs 3](/images/Getting started with CPLDs 3.jpg)

Now that the board was clean (and complete) I cracked on with the Hackshed tutorials.  Starting with the "Hello world!" of electronics - blinking an LED:

![Getting started with CPLDs 4](/images/Getting started with CPLDs 4.jpg)

The tutorials are a great way to get up and running with the Altera software very quickly.  I wouldn't say the software is complicated - its just not very intuitive for someone who has't used it before.  [Bil Herd](http://en.wikipedia.org/wiki/Bil_Herd) over at [Hack a Day](https://hackaday.com/) has started a series on [Programable Logic](https://hackaday.com/2014/06/24/programmable-logic-i-plapal/) which is also well worth checking out (and not just because it's Bil Herd doing it).

As Bil would say "Keep Hacking!".