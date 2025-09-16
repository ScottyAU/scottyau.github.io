---
layout: post
title:  "ATX Bench Supply"
date:   2014-03-23 20:38:00 +1000
tags:   Power Supply, Electronics
---

I've been starting to fiddle more and more with electronics of late, and I've realised that at some point I'm going to have to power some stuff off something other than a Arduino/Launchpad etc.

In learning about power supplies and the electronics inside them, I've realised there are a lot of options for a bench top supply.  While I definitely plan to have a bit of play (evident from the regulators and other bits that arrived in the mail last week), one starting option was to take an ATX PC power supply and use that as a bench supply.  This will give me the 12v/5v/3.3v I need at the moment - and is pretty cost effective (if you already have the ATX supply).  I looked around at a few examples on the internet (there are heaps!) but the one I like the most was the Dangerous Prototypes ATX Breakoutboard.  I ordered one from Seeed Studio along with an Acrylic Case and waited by the mailbox.

The bits turned up last week and I got a chance to sit down today and put it together.

![ATX Bench Supply 1](/images/ATX Bench Supply 1.jpg)

So looking at the docs for the ATX BB it notes that it comes with a 9Watt load resistor, that is not required with most modern supplies (it's used as an increased load on the 5v rail so the supply with start).  So with this in mind I plugged the ATX BB into the supply and powered it up!  Worked first go without the 9W load resistor.  I metered the voltages across the various terminals and all were spot on.

If you've ever put a PC together you'll know how many extra connectors there are on an ATX supply besides the motherboard connector.  If not you can see them in the picture above - everything other than the wires in the black mesh.  So I opened up the supply to have a look at how easy this might be.

PLEASE NOTE - I was warned by several nice guys to be careful of the capacitors inside once the supply has been on - as they can hold quite a voltage.

![ATX Bench Supply 2](/images/ATX Bench Supply 2.jpg)

I then removed some cable ties and spaced the cables out.  Then I removed the 4 screws holding the PCB in and lifted it to one side.  Getting to the 5v (red) and Ground (black) cables easy enough so they could be removed fully.  However getting to rest of the cables at the base was not possible thanks to the capacitors and other bits on the main PCB.  So they were grouped together by voltage and cut off.  They were then taped together and heat shrink applied.

![ATX Bench Supply 3](/images/ATX Bench Supply 3.jpg)

Once this was done I carefully plugged the ATX BB back in and powered up the supply.  No magic smoke - so I put the supply back together.

![ATX Bench Supply 4](/images/ATX Bench Supply 4.jpg)

Not only is that a lot tidier, but I've now also got a chunk os spare wire in the drawer to boot.  Plugged it all back in - all done!

![ATX Bench Supply 5](/images/ATX Bench Supply 5.jpg)