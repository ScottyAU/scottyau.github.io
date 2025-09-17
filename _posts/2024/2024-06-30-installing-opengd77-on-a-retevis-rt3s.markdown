---
layout: post
title:  "Installing OpenGD77 on a Retevis RT3s"
date:   2024-06-30 16:43:00 +1000
tags:   Amateur Radio, Electronics
---

So the [Brisbane Amateur Radio Club (BARC)](https://barc.org.au/) that I joined has been playing with a few different digital modes - and one of them is Digital Mobile Radio or DMR.  The [club's page on DMR](https://barc.org.au/articles/dmr/) has some information on how they got started, the radio most members have bought (Retevis RT3S) and there is also a [page with code plugs](https://barc.org.au/codeplugs/) configured with local repeaters to help get people going.

The RT3S is a pretty cool little HT for $80-90.  It's UHF/VHF, has GPS, APRS (TX only) and DMR support - and it runs [OpenGD77](https://www.opengd77.com/) - an opensource firmware that a number of club members have flashed their HT with.

This all looked pretty cool - so last week I ordered an RT3S off the Retevis eBay store and it showed up a few days later.  I opted for the pack with the programming cable:  

![Installing OpenGD77 Retev9s RT3s 1](/images/Installing OpenGD77 Retev9s RT3s 1.jpg)

![Installing OpenGD77 Retev9s RT3s 2](/images/Installing OpenGD77 Retev9s RT3s 2.jpg)

The radio itself is built pretty well with my only complaint being it doesn't have USB-C (or any direct DC) source of charging.  You need to stick it in the dock that it comes with.  I'll continue to look for options to address this.

![Installing OpenGD77 Retev9s RT3s 3](/images/Installing OpenGD77 Retev9s RT3s 3.jpg)

There is an [install thread](https://www.opengd77.com/viewtopic.php?f=19&t=2380) and also a [YouTube video](https://www.youtube.com/watch?v=65SEEGfYz4M) on how to install OpenGD77 on this radio.  While both are a little over a year old - the only real differences at this point are the versions of files linked/used.  I gave the radio a full charge, and in the meantime installed the Retevis CPS software, and the USB driver.  

Once the radio was fully charged I plugged it in to start the install process (I had no intention of using this radio with the stock firmware - I can however flash back to it if required according to the documentation with the backups I took).  This was the first hiccup I encountered that seems to catch quite a few people - I had the wrong USB driver.  As [highlighted in this thread](https://www.opengd77.com/viewtopic.php?f=19&t=4118), I had the "Digital Radio in USB mode" - not the "STM Device in DFU mode" under Windows Device Manager.  To fix this I used the Windows 10 driver (even though I am using a laptop with Windows 11) linked from that thread - right clicked the device in Device Manager, and selected Update Driver.  I then manually choose the location to look for the driver (specifying the driver downloaded from that thread).  

With that sorted the HT showed up in the Retevis CPS software and I could backup both the factory code plug and more importantly the calibration data in the radio.  Hit the "Read" icon, and once the config is downloaded save a copy somewhere safe.  Everything says flashing the firmware shouldn't touch the calibration data - but to back it up anyway just in case as it should be unique to my HT.  With the radio plugged in and Retevis CPS open you then need to hit "Control" + "t".  It took me a second to realise this wasn't on the HT - just on your keyboard!  Doing so brings up the hidden test menu and you can save a local copy of your "test" (read calibration) data somewhere safe with the factory code plug:

![Installing OpenGD77 Retev9s RT3s 4](/images/Installing OpenGD77 Retev9s RT3s 4.png)

With that done I was ready to open the OpenGD version of the CPS software and get to flashing.  The first step was to set the HT type in the "Radio type" menu:

![Installing OpenGD77 Retev9s RT3s 5](/images/Installing OpenGD77 Retev9s RT3s 5.png)

Then under the "Extras" menu select "Firmware loader".  You'll need to set the Radio type again, select the donor firmware file (MD9600-CSV(2571V5)-V26.45.bin) which you can find [linked in the OpenGD77 install thread](https://www.passion-radio.com/index.php?controller=attachment&id_attachment=760), this file is needed for DMR to work with OpenGD77.  And then lastly the [latest OpenGD77 firmware file](https://www.opengd77.com/downloads/MDUV380_DM1701/Firmware/Latest/) you want to flash (OpenMDUV380.bin).  Once you select the Open firmware file the flashing process will begin:

![Installing OpenGD77 Retev9s RT3s 6](/images/Installing OpenGD77 Retev9s RT3s 6.png)

This will take a couple of minutes.  When mine completed I saw "Settings Updated" on my HT:

![Installing OpenGD77 Retev9s RT3s 7](/images/Installing OpenGD77 Retev9s RT3s 7.jpg)

Now it's time to do a full backup of the entire flash on the HT - this is what you will need to restore before you flash back to stock Retevis firmware.  Under the "Extras" menu again click on "OpenGD77 Support", and then click "Backup Flash" and save this file somewhere safe.  This will take a few minutes to complete:

![Installing OpenGD77 Retev9s RT3s 8](/images/Installing OpenGD77 Retev9s RT3s 8.png)

Once complete I also did the "Backup MCU ROM" and "Backup Registers".  I then hit "Write codeplug" to write an OpenGD based code plug to the radio.  The stock existing Retevis based code plug does not work with OpenGD.  

As covered in the YouTube video I also hit "Install satellite keps":

![Installing OpenGD77 Retev9s RT3s 9](/images/Installing OpenGD77 Retev9s RT3s 9.png)

Followed by "Write voice prompts" - using the "[english_AU_nicole-1.5_UV380-like.vpr](http://Fileenglish_AU_nicole-1.5_UV380-like.vpr)" file (the 1.5 denotes speed of the voice).  I also then installed a callsign databased as covered in the YouTube video (Extras - Download callsign database), using a Region filter of 505 and increasing the data record length to "50" and then writing to the radio:

![Installing OpenGD77 Retev9s RT3s 10](/images/Installing OpenGD77 Retev9s RT3s 10.png)

At this point the radio was running OpenGD77!  As mentioned our radio club has an [OpenGD77 based code plug](https://barc.org.au/codeplugs/) that has a bunch of local repeaters and FreeDMR talk groups configured as well as APRS setup.  I just needed to enter my callsign and digital radio ID and write that code plug to be fully configured!

At this point I did a couple of things - I turned on GPS, and then APRS (in the settings menu on the HT itself) and once GPS got a lock I had an APRS beacon show up within a few minutes.  I then tried the DMR side of things - setting the radio to our local DMR enabled repeater and using Talk Group 5050 that we use for our Monday night DMR net.  I then used another device (more in another post) to transmit on FreeDMR and TG-5050 and it came through - success! 

![Installing OpenGD77 Retev9s RT3s 11](/images/Installing OpenGD77 Retev9s RT3s 11.jpg)