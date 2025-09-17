---
layout: post
title:  "Rolling your own Marlin build"
date:   2021-02-07 19:21:00 +1000
tags:   3d printing
---

So I wanted to have a crack at rolling my own firmware build for my Ender 3 V2.  Marlin is pretty awesome - and setup in a way that makes it pretty user friendly.  I would start with [this video](https://www.youtube.com/watch?v=neS7lB7fCww) from Teaching Tech.  He goes through how to build your own firmware - which I 100% used as a base.  I did a few things slightly differently and probably will continue to tweak as I go.  If you just use his video and follow it you will absolutely end up with a useable firmware.  This post is as much for me as anyone else that might stumble across it - on what options I used.  

So start by making sure you have [git](http://git-scm.com/) and [Visual Studio Code](https://code.visualstudio.com/) installed and up to date.  Open code and install the PlatformIO IDE extension:

![Rolling your own Marlin build 1](/images/Rolling your own Marlin build 1.png)

I then checked out the Marlin code and switched to the [bugfix-2.0.x](https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x) branch that Teaching Tech suggests in his video:

```
git clone https://github.com/MarlinFirmware/Marlin.git
git checkout bugfix-2.0.x
```

You could skip this and just download the zip file of source from GitHub like the video - I just tend to default to using git.  I then downloaded the configuration zip that is mentioned in the video (you can find it in the /config/readme.md) and has a bunch of configs for different printers - I used the bottom one as that matches the branch I am using:

![Rolling your own Marlin build 2](/images/Rolling your own Marlin build 2.png)

I then extracted the zip and jumped to:

`\Configurations-bugfix-2.0.x\config\examples\Creality\Ender-3 V2`

I copied the contents of this directory to Marlin directory, inside the Marlin folder when I checked the code out.  Overwrite any files that already exist.

At this point I flicked back to code and opened the folder I had just created when checking out Marlin.  There are a couple of config options you need to edit as suggested in the video, the three files and the options I changes are:

**\Platformio.ini**

Changed default_envs to be this to match my Ender 3 V2 with the 4.2.2 board:

`default_envs = STM32F103RET6_creality`

**Marlin\src\Configuration.h**

Find the following lines and uncomment to enable my BLTouch:

```
#define BLTOUCH
#define AUTO_BED_LEVELING_BILINEAR
#define Z_SAFE_HOMING
```

Find the following line and uncomment and change the offsets to match those of the [BLTouch mount](https://www.thingiverse.com/thing:4462870) I used off thingiverse (in the description on that page):

`#define NOZZLE_TO_PROBE_OFFSET { -42, -10, 0 }`

**Marlin\src\Configuration_adv.h**

Find the following line and uncomment:

`#define BABYSTEP_ZPROBE_OFFSET`

You are now ready to try and build.  Click the little "tick" in the bottom bar in code and the build will kick off.  The very first one you do will take a couple of minutes while it downloads a few bits - but subsequent builds should be 30 seconds or so.  

The firmware file created will be in:

`\.pio\build\STM32F103RET6_creality`

You want the firmware-[date]-[time].bin that matches the timestamp of when you just did the build.  Copy this file over to an empty micro SD card and whack it in the printer.  Turn it on, and it will update and when finished jump to the menu.  You can check the version by going to Control and then Info down the bottom:

![Rolling your own Marlin build 3](/images/Rolling your own Marlin build 3.jpg)

At this point I also updated the LCD firmware too - since I could (I'm not actually sure how to check it's version - so just did it anyways).  The video is a better guide here and I did exactly as suggested - copied the DWIN_SET folder from the config examples directory over to an empty SD card, took the LCD apart and put it in the SD slot and turned the printer on.

Any nothing happened - it just booted up like normal. 

After a minute trying a few things I took another look at the SD card and it was formatted FAT and not FAT32.  I re-formatted the card FAT32, copied the DWIN_SET folder back over and tried again and it worked first go.

At this point I had a printer ready to setup.  I reset all settings as suggested in the video by going to Control and then Restore Defaults, and then hit Store Settings to save a fresh copy.  I then tried an auto home and while X and Y worked fine - Z with the BLTouch did not.

Turns out the way the firmware is configured by default and the way Teaching Tech does it in his video too meant I needed to change my BLTouch connections on the control board to put the Z Stop into the ZStop sensor header on the board (previously I had it all in the dedicated BLTouch header).  The black/white pair below:

![Rolling your own Marlin build 4](/images/Rolling your own Marlin build 4.jpg)

This makes sense - to leave it all in the dedicated BLTouch header I'd need to change the pin setup in the config files for the Z Stop.  Creality must do this in their build config as using their stock BLTouch enabled firmware only worked with the BLTouch wired to the header as mine was initially.  I switched this wiring over and the ZStop / BLTouch worked as expected.  

I did an autohome and then a bed level.  I then set the Z offset as discussed in the last post about the BLTouch.  It was slightly different this time (-1.97 vs -1.99) but I did have to move the printer around a bit to get at the control board to change the wiring.

I now have a printer that prints exactly as it did before... :)  But it is running firmware I built - that I can continue to tweak as I learn!