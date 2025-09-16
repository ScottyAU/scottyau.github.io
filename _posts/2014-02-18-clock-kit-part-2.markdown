---
layout: post
title:  "Clock kit Part 2"
date:   2014-02-18 21:35:00 +1000
tags:   LED Clock, Electronics
---

With the schematic in hand I was itching to get my solder on.  The board itself appears to be somewhat generic, in that not all components labelled on the board need to be fit for this clock to be complete.  Using the schematic and the parts received list we were able to figure out what needed to go where.

Before I go through what goes where, a general note is that I soldered all of the SMD components on the back of the board, starting in the middle working my way out.  Then all of the SMD components on the front.  And then the large components on both sides as it made sense.

As mentioned, the board is two sided.  The back of the board is the tricky one of the two.  All of the big components are labelled clearly and so are straight forward.  The only exception is the power supply components - which can go at either end of the PCB, it's completely up to what suits you.  The SMD components needed to be worked out using the schematics and then a meter to see what pins/pads matched.

The following were soldered onto the back of the board:

* C1   - 10μF
* C2   - 30pF
* C3   - 30pF
* C11 - 0.1μF
* C12 - 30pF
* C14 - 0.1μF
* C15 - 10μF
* C26 - 0.1μF
* R1   - 10kΩ
* R2   - 10kΩ
* R3   - 10kΩ
* R4   - 10kΩ
* R6   - 1kΩ
* R11 (or R12 or R13) LED - 270Ω- can choose 1 of these 3 - just need to match it below
* Q1   - Transistor
* BT   - Battery
* U1   - STC12C5620AD
* U2   - LPD6803
* U3   - DS3231
* Y     - Crystal
* Bell
* T1 (or T2) - Temp Sensor (using 3 wire ribbon cable to extend)

Power supply bits (I chose the right side looking at the back of the clock):

* C16 - 0.1μF
* C19 - 100μF
* C21 - 100μF
* C22 - 100μF
* R7   - 4.7kΩ
* USB header

On the front of the board (the side with the display) everything is pretty much as labelled.  All resistors need to be fitted and are all 10k.  All capacitors also need to be fitted and are all 0.1micro caps.  The IR receiver  goes where marked.  All IC's under the display blocks need to go on.  The display segments are fitted with the decimal point at the bottom (the bottom matching the text layout on the board).  The LED's that act as separators will need to use the common labelled pin and the pin matching the R11/R12/R13 on the back that you chose while doing the back of the board previously(just use a meter to check).  There's also a 4 pin programming header - which I'll get to in a minute.

While soldering the display blocks in I powered it up to check each one, and they were working - but displaying some weird characters.  All segments of the display blocks did work though so I cracked on and soldered all 6 display blocks:

![LED Clock Pt2 1](/images/LED Clock Pt2 1.jpg)

Once complete, I plugged it in and got this:

![LED Clock Pt2 2](/images/LED Clock Pt2 2.jpg)

It took a minute to realise the display was inverted.  Instead of turning on the segments to display a digit, it was turning on the inverse segments.  So the above should read 00:02:09

This was again a point I had to "phone a friend".  After desoldering a display block and flipping it to no avail, we went digging through the documentation we had.  BINGO!  The VFD clock that this clock is based off has different drivers for the tubes - which invert the signal they receive!  This hadn't been taken into account in the source code I was sent by the seller (it had just been used as is by the looks of it), and so instead of setting the bits to turn on - its actually setting the bits that should be turned off for each digit.

Realising that the STC12C5620AD would need to be flashed with new code at least meant that the clock was physically put together correctly.  I've started getting setup to program the STC12C5620AD with new code - that will be covered in Part 3.