---
layout: post
title:  "Dev board Stage 1 - Part 1"
date:   2015-02-10 21:31:00 +1000
tags:   Electronics, Programming, Learning
---

A while ago one of my best mates gave me a dev board that he had done some work with that he thought I might like to do something with.  It's sat on my shelf for quite a long time, but this week I decided that it would be my next project.  This is not intended to be a short project, but if it goes the way I hope it will, it should be a medium term one with both some hardware and software involved.  Time will tell.

The board uses a [ColdFire MCF52235](http://www.freescale.com/webapp/sps/site/prod_summary.jsp?code=MCF5223X) microcontroller, which has an SPI interface for programming called EzPort.

"Stage one" of this project consists of being able to flash this micro with new firmware over SPI using my BusPirate.  Initially i'll need to figure out the connection and can then test it with the just a console to the [BusPirate](http://dangerousprototypes.com/docs/Bus_Pirate).  Once that works i'll need to write some code to get the programming working.

According to the data sheet, to connect the BusPirate to the EzPort on the micro the following connections are required:

| BusPirate | EzPort |
|:---|:---|
|MISO|QSPI_DOUT|
|CLK|QSPI_CLK|
|MOSI|QSPI_DIN|
|CS|EZPCS|
|VPU|3.3V|
|GND|GND|

It should look something like this:

![Dev board Stage One Part 1 1](/images/Dev board Stage One Part 1 1.jpg)

Again referring to the micro datasheet we can figure out the SPI parameters for configuring the BusPirate in SPI mode:

``` 
HiZ>m
1. HiZ
2. 1-WIRE
3. UART
4. I2C
5. SPI
6. 2WIRE
7. 3WIRE
8. LCD
x. exit(without change)

(1)>5
Set speed:
 1. 30KHz
 2. 125KHz
 3. 250KHz
 4. 1MHz

(1)>2
Clock polarity:
 1. Idle low *default
 2. Idle high

(1)>1
Output clock edge:
 1. Idle to active
 2. Active to idle *default

(2)>1
Input sample phase:
 1. Middle *default
 2. End

(1)>1
CS:
 1. CS
 2. /CS *default

(2)>2
Select output type:
 1. Open drain (H=Hi-Z, L=GND)
 2. Normal (H=3.3V, L=GND)

(1)>1
Ready
SPI> 
```

With this done it was back to the data sheet again to look at how to enable the EzPort and interact with it to verify our setup.  Setting CS active low while powering up the board should be enough to enable the EzPort on the micro.  So on the BusPirate:

```
SPI>[
/CS ENABLED
```

I then powered up the board.  Time to see if we can read/write to the micro!  As suggested in the data sheet we'll read out the status register, set the write register and then read out the status register again to see if our change worked:

```
SPI>{0x05 0x00]
/CS ENABLED
WRITE: 0x05 READ: 0xFF 
WRITE: 0x00 READ: 0x00 
/CS DISABLED

SPI>[0x06]
/CS ENABLED
WRITE: 0x06 
/CS DISABLED

SPI>{0x05 0x00]
/CS ENABLED
WRITE: 0x05 READ: 0xFF 
WRITE: 0x00 READ: 0x02 
/CS DISABLED
```

It works!  Given the connection works I made up a slightly more permanent cable to replace the BusPirate probes:

![Dev board Stage One Part 1 2](/images/Dev board Stage One Part 1 2.jpg)

Now the connection is sorted it's time to look at erasing and then programming the micro in Stage One - Part 2.  There was a little more trial and error involved in getting to this point - but nothing that was terribly interesting.  

Initially while developing the code to flash the micro, I will use an image that was provided.  Once the code for that is sorted I'll look at flashing something different (Stage 2)!