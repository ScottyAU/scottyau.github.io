---
layout: post
title:  "Bare Bones ATMega168"
date:   2014-06-05 15:30:00 +1000
tags:   Electronics, Programming, Learning
---

I've been playing quite a bit with Arduino based stuff over the last while.  It's an awesome way to get started without a huge amount of low level knowledge of the micro required to get an LED to blink.  I wanted to try some bare bones bits though with some ATMega's as well.   I found a few different tutorials online that explain the gap that the Arduino bootloader fills.  One of the ones I liked the most is the [Hack a Day series on AVR programming](http://hackaday.com/2010/10/23/avr-programming-introduction/).

I ordered a few [ATMega168's](https://core-electronics.com.au/store/index.php/atmega168-atmel-avr-microcontroller.html/?acc=34173cb38f07f89ddbebc2ac9128303f) from [Core Electronics](https://core-electronics.com.au/store/index.php?acc=34173cb38f07f89ddbebc2ac9128303f).  I've been buying a bit from them lately.  They are here in Australia, with pretty good prices and very fast shipping.

As for the AVR programming hardware I decided to use my [BusPirate](http://dangerousprototypes.com/docs/Bus_Pirate) (fully supported by AVRDude).
So I read through the tutorials and got to the section in Tutorial 02 where it's time to connect up and program the ATMega168.  Dangerous Prototypes have a full page on [using the BusPirate as an AVR programmer](http://dangerousprototypes.com/docs/Bus_Pirate_AVR_Programming).

There were two bits that I had to change to get the setup to work for me with my BusPirate.  Firstly I had to remove the connections to 5v and GND for pins AVCC (20) and AGND (22) to program the ATMega168 and have it work once programmed.  The other change was that I had to make sure the GND from the BusPirate was connected for it to program the micro.  I was initially trying to use an external 5v source with the GND and 5v probes from the BusPirate completely disconnected, but the programming failed consistently.  As soon as I connected the GND from the BusPirate everything worked flawlessly.  Once programmed I could just use my external 5v supply and watch the LED blink!

Before programming the ATMega168 I verified the connections were correct using this command to see if avrdude could read the device signature:

`avrdude -c buspirate -P /dev/tty.usbserial-AXXXXXXX -p m168 -v`

Once that successfully worked (that was the command I was using to track down the two issues mentioned previously) I used this command to actually program the ATMega168:

`avrdude -c buspirate -P /dev/tty.usbserial-AXXXXXXX -p m168 -U flash:w:main.hex`

Once the ATMega168 was programmed giving it 5v made the LED blink - SUCCESS!!!

![Bare Bones ATMega168 1](/images/Bare Bones ATMega168 1.jpg)

I then went on and walked through part 3 and 4.  I managed to write most of the code talked about in part 4 with only a few pointers required.

![Bare Bones ATMega168 2](/images/Bare Bones ATMega168 2.jpg)

Most of the content in these AVR tutorials was a lot easier to digest after doing the edx course that I [previously mentioned]({% post_url 2014/2014-04-26-edx-ut.6.01.x %}).  