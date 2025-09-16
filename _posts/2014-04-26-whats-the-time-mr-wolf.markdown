---
layout: post
title:  "What's the time Mr Wolf?"
date:   2014-04-26 16:50:00 +1000
tags:   Electronics, Programming, Learning
---

So for the last couple of months the bit of bench time I've been able to get has all been spent on the edx course I mentioned in my previous post.  There was quite a bit of content to get through before the course wrapped up, so to get it done in time I wasn't letting myself play with any other projects or bits.  I was however ordering bits and pieces here and there which have slowly started to arrive.  Now that the course is done I've got time to play with what's arrived!

Something I should point out is that while all (or at least some) of the individual bits I've ordered will hopefully end up working together, one of the most common ways to test them individually seems to be with an Arduino.  I have almost no experience with Arduino's so it's a good chance to get to do a little more Arduino too!

One of the things I ordered was a [Tiny RTC v1.1](http://www.dfrobot.com/wiki/index.php/Real_Time_Clock_Module_(DS1307)_V1.1_(SKU:DFR0151))  

![Whats the time Mr Wolf 1](/images/Whats the time Mr Wolf 1.jpg)

The DS18B20 you see in the picture above doesn't come with the kit - I ordered that separately.  The TinyRTC module has a spot to solder this guy in (as mentioned on the wiki page for the module) with the required pull up resistor already onboard.  All that's needed is to connect to the DS pin to read data from the sensor.  I soldered the headers and DS18B20 on and connected it to my Arduino Uno as shown on the wiki page:

![Whats the time Mr Wolf 2](/images/Whats the time Mr Wolf 2.jpg)

There were two libraries I had to add for the TinyRTC sketch on the wiki to work (DS1307 & OneWire).  I changed the sketch to set the correct time (it shipped without the battery installed as can be seen above) and uploaded the sketch.  The time set correctly and the serial console showed the output of the RTC incrementing correctly.

Then I went looking at what was needed to read the temperature from the DS18B20.  [This page](http://milesburton.com/Main_Page?title=Dallas_Temperature_Control_Library) has all the detail needed.  I had to add another library (DallasTemperature). I then restarted the IDE and added in code to the sketch to read the data from the DS pin to get the current temperature. I now had the temperature also displaying in the serial console.  I tidied the sketch up a bit and also tidied up the output to the serial console:

![Whats the time Mr Wolf 3](/images/Whats the time Mr Wolf 3.png)

The last thing I wanted to try while I had this guy plugged in was the [Saleae Logic Analyser](https://www.saleae.com/logic16) I also bought over the last couple of months.  The Arduino is using I2C to talk to the the RTC module, so I connected the two required pins to the logic and plugged the logic into my Mac.  I opened the software, added an I2C analyser with the appropriate pins and recorded a sample:

![Whats the time Mr Wolf 4](/images/Whats the time Mr Wolf 4.png)

Pretty straight forward!

I've got a few more bits to connect up and test, and a few more bits still on their way.  I've got a few ideas of things I would like to build, time to flesh a couple of them out.  Cool beans.