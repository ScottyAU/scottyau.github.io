---
layout: post
title:  "Bed levelling upgrades"
date:   2021-01-26 08:30:00 +1000
tags:   3d printing
---

 So after getting the filament sorted - the next thing to look at was bed levelling.  I was trying to get a consistent first layer - and unsurprisingly Teaching [Tech had a video](https://www.youtube.com/watch?v=Ze36SX1xzOE) and a [whole website devoted to bed levelling](https://teachingtechyt.github.io/calibration.html#firstlayer)!  He goes through it in the video but his site generates a gcode file that will print 5 squares by default to help you see if your first layers will go down consistently in each part of the bed.  

This alone helped me quite a lot - prior to this I was just doing the manual bed level and kicking off a print.  What I was finding though was that I couldn't quite get it perfect - and it was changing a little each day.  I'd get it pretty good, do a bunch of prints that were ok and then come back a day or two later and need to re-level again.  

So I've done my first two upgrades!  The first was a [spring and levelling nut upgrade kit](https://www.amazon.com.au/gp/product/B08K2PXXJ5/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1).  This was super easy to put in - and very much holds the level that is set longer than the stock springs/wheels did for me at least:

![Bed levelling upgrades 1](/images/Bed levelling upgrades 1.jpeg)

![Bed levelling upgrades 2](/images/Bed levelling upgrades 2.jpeg)

Once this was in I levelled again and tried the first layer gcode from Teaching Tech's site with pretty awesome results:

![Bed levelling upgrades 3](/images/Bed levelling upgrades 3.jpeg)

The bed itself is not perfectly flat as covered in the video - plus I really like the idea of being able to programmatically auto bed level - so I bought a BLTouch too :)

This one is a slightly more detailed install - I printed a [mount off thingiverse](https://www.thingiverse.com/thing:4462870) and got to work installing the BLTouch.  I installed the mount, mounted the BLTouch and ran the extension cable to the control box underneath using the existing cable sleeve.  It's worth noting you need to order an extension cable if you buy a BLTouch for an Ender3 V2 - the default cable length is way too short.  I cut the 2m cable and re-terminated it to the right length - about 1.5m would be perfect.  You could easily just loop that last bit up though if you don't want to re-terminate the cable.  The other cool bit is that the the new control board in the Ender 3 V2 has a dedicated port for a BLTouch - no adapter board on the display port required so it's plug and play.  

![Bed levelling upgrades 4](/images/Bed levelling upgrades 4.jpeg)

![Bed levelling upgrades 5](/images/Bed levelling upgrades 5.jpeg)

All guides recommend you disconnect the Z axis stop when you add a BLTouch as it becomes the Z stop.  I didn't initially and saw why people suggest this needed to be done - the Z stop switch did occasionally trigger and the BLTouch/printer can't handle it and bugs out.  So I have now unplugged my Z stop switch :)  The last bit required to get going with the BLTouch is a Marlin build with it enabled.  

This is another rabbit hole that I am currently exploring - custom firmware.  That's a future post though.  For the moment Creality do produce a firmware build with the BLTouch enabled.  Going to the Creality site, the downloads section and then selecting the Ender 3 V2 gives you a bunch of files that are a. little confusing on first glance.  I actually flashed the wrong firmware because I didn't understand this and thought I was just grabbing the latest firmware - not realising it was for a different board revision.  After flashing this wrong firmware the printer would just boot to a blank screen.  

So as of writing the filenames are something like:

**4.2.2 Ender-3 v2 Marlin2.0.1 BLtouchV1.1.1without adapter board firmware.rar**

The first set of numbers are the board revision (I have a 4.2.2 - and not a 4.2.7 as I initially downloaded).  As mentioned this board has a dedicated BLTouch port too - no adapter board required - which is also mentioned in the filenames.  So go for the one that says without adapter board.  

Luckily nothing was bricked - I just had to grab the right firmware (filename above) and put it on an empty micro sd card and name it something new (the Ender bootloader needs a unique filename to flash a new firmware).  This brought the printer back to life with a new "Level" option on the main menu and the BLTouch initialising when you turn the printer on:

![Bed levelling upgrades 6](/images/Bed levelling upgrades 6.jpeg)

So at this point I hit the level option on the menu - and I have to say it's pretty awesome watching your printer setting a level mesh.  This failed the first couple of times thanks to the Z Stop switch still being connected and triggering once or twice as mentioned above.  Unplugging it fixed that.  

The last part is setting the Z Offset.  This is the difference between where the BLTouch triggers and your nozzle/hot end.  Again Teaching Tech has an [awesome video explaining this](https://www.youtube.com/watch?v=fN_ndWvXGBQ) - but he uses custom firmware with a Z Offset tool (which I don't have just yet).  I just used the auto home option (which will set the printer up to where it thinks it at zero including any z offset) and then adjusted the z offset there to get it to the right height for my setup (-1.99 for me) with a bit of paper like manual bed levelling.  

A word of warning - you are supposed to be able to live adjust the Z offset during a print - and I 100% have the option in the stock firmware I am running at the moment and tried it but the printer didn't seem to like it too much.  It went down way to much when I was adjusting it just 0.01 at a time killing the print.  This was confirmed by stopping the printer and trying the exact same setting before starting a print which would work.  So I stuck to setting the Z offset prior to any prints.

The end result is some super stellar first layers - they go down smooth and consistent across the bed with the perfect amount of "squish"!

![Bed levelling upgrades 7](/images/Bed levelling upgrades 7.jpeg)