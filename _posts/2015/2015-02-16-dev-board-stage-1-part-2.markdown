---
layout: post
title:  "Dev board Stage 1 - Part 2"
date:   2015-02-16 21:17:00 +1000
tags:   Electronics, Programming, Learning
---

Nowadays I'm a Python guy, so as per the previous post once I had the basics working with the BusPirate using it's inbuilt console I immediately went looking for Python based options for using the BusPirate.  I pretty quickly landed on [pyBusPirate](https://github.com/audiohacked/pyBusPirate).

After cloning the code I jumped straight into the SPI samples and pretty quickly realised that while I could read the Python - I didn't actually know why the code was doing what it was doing.  I had no idea why different bytes were being sent, or what was being returned as a result.

So I took a breath and a step back.  I then went and read about the [BusPirate in Bitbang mode](http://dangerousprototypes.com/docs/Bitbang), and then specifically [SPI(Binary) mode](http://dangerousprototypes.com/docs/SPI_(binary)).

Things make much more sense now - why each byte is being sent and what's being returned (or expected to be returned).  Those links make it pretty clear what I need to do to setup the BusPirate in SPI with my required options for this particular chip.

So I'm now looking at two main operations: write and erase.  The third operation i'll add in to support the first two is read, so I can check the result of a write or erase command.

I'll need a few bits of code to take in some options about which operation to call and the file associated (either to read to or from).  I'll also need to add the necessary bits in to set the registers for the chip for each operation.  That should be about it to get things moving with bulk write or erase commands.

Hopefully the next post has a picture of the board running the firmware I was given with the board!