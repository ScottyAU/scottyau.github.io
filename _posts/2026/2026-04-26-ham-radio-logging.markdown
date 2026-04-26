---
layout: post
title:  "HAM Radio Logging"
date:   2026-04-26 09:00:00 +1000
tags:   Amateur Radio
---

Once I started getting into HF Amateur radio, and then very quickly [Parks on the Air](https://pota.app) I realised I needed to think about logging.  I'd been logging with pen and paper while on UHF/VHF - mainly nets so I could keep track of my spot in the list and also keep a bit of an idea of what nets were busier and who were the regulars.  This wasn't going to cut it once I started with HF.  I went down quite a rabbit hole when it came to options for logging in HAM radio, and actually ended up [doing a few slides](/files/Amateur Radio Logging.pdf) and a short talk to the [Brisbane Amateur Radio Club](https://barc.org.au) last year.  This blog post is the follow up that captures how I am logging right now as of April 2026.

Logging contacts in HAM radio can be for a number of reasons:

- A list of conacts or QSOs made for your own records - who you've worked before where and on what bands/modes
- Confirming QSOs with the other party, including electronic or paper QSL cards
- Part of a program where log submission is required (Parks on the Air, Summits on the Air etc)
- Contests which require log submission

I say rabbit hole as like most of HAM radio there are alot of options, some more recent and maintained than others, some that play nicely with each other and some that don't - including the different logging formats.  Spoiler alert - I have ended up with a "set" of apps/logs as there wasn't a single option that met all of my goals.  My goals covered the first three of the four bullets above.  The only contests I have done so far have been with the club so we've logged that collectively at the club shack and submitted.  I do intend to contest more in the future so I will need to add something in there if none of my existing apps support the contests and formats required.  

I had two primary use cases:

- Logging contacts at my QTH (home) - Phone, Digital and CW
- Logging contacts when portable for POTA (and subsquently SOTA)

I'll start with the second as it's much easier.  There are multiple apps both mobile and web that support POTA and the other portable programs (SOTA etc) and I looked at a few, but there is one that is hands down the best - [Ham2K Portable Logger (PoLo)](https://polo.ham2k.com/) by Sebastián KI2D.  It's exactly what you would expect from modern software, not just easy to use but intuative.  You can open it up and be on the air logging contacts in seconds, has a silly amount of [shortcuts](https://polo.ham2k.com/docs/polo-features/tips-and-tricks/) that make it a pleasure to use (eg click on someone in the spots page to auto populate your log for a Park 2 Park) and is updated all the time.  As of time of writing it works on Android and iOS (that includes modern macs that can use apps from the app store).  It has alpha syncing capability if you are using the app on more than one device and has a super active discord both for the app as well portable operation more generally.  If you do portable operation and have not tried Ham2k Polo do yourself a favour and try it now.  I log on my mobile phone and when finished export my adif log file to my OneDrive (all cloud storage supported plus lots of other options) to upload to the POTA website when I get home.  The POTA website doesn't allow uploads from a mobile phone and does not yet have an API for upload.  I know that if/when it does that will be rolled into Ham2k PoLo.

![HAM Radio Logging 1](/images/HAM Radio Logging 1.png)

For logging at home I looked at a lot more options, and here is my short summary:

- [Ham2K Polo](https://polo.ham2k.com/) – Great for portable, but not QTH (mobile only and aimed at portable - for now)  
- [HAMRS](https://hamrs.app/) – What I have ended up with – free trial but paid ($20/year).  Cross platform and browser based too.
- [World Radio League (WRL)](https://worldradioleague.com/) – Another great option that works well – free and paid tiers, cross platform and browser based, heaps of features
- [qrz.com](https://www.qrz.com/) – Online record for QSO confirmation.  No direct integration with HF rig. 
- [ARRL Logbook of the World (LOTW)](https://www.arrl.org/logbook-of-the-world) – QSO confirmation and competitions (using digital certificates to sign QSO’s).  Requires verification when signing up.
- [ClubLog](https://clublog.org/)  - QSO confirmation and competitions (create/join clubs)
- [eqsl](https://www.eqsl.cc/) – Name says it all (electronic QSLs)
- [GridTracker](https://gridtracker.org/) – great program to integrate with WSJTX and can auto upload logs – not a logger per say (but does keep a copy on disk)
- [Log4OM](https://www.log4om.com/) – looks very feature rich but Windows only (I wanted mobile options)
- [N3FJP](https://www.n3fjp.com/) – Windows only (and paid)
- [N1MM](https://n1mmwp.hamdocs.com/) – contest only logger

I did go back and forth initally between HAMRS and WRL, settling on HAMRS.  It's simple and easy to use and does most of what I am after (would be nice to have auto export to eQSL and/or clublog).  It is paid after the free trial, and I like supporting the HAMS that built and maintain the software I use everytime I turn on my rig at home.  

My workflow currently looks like this (complicated I know):

![HAM Radio Logging 2](/images/HAM Radio Logging 2.png)

If I am doing Phone or CW at home I will often have [FLRig](https://hb9tzu.ch/en/Flrig/) running which will do rig control and sync with HAMRS.  So as I change bands, frequencies, modes etc that all auto populates into HAMRS.  I just need to fill out the callsign and signal report:

![HAM Radio Logging 3](/images/HAM Radio Logging 3.png)

If I have done a portable operation I will have an ADIF file on OneDrive that I import into my portable logbook in HAMRS.  

And lastly if I am doing digital at home I will have [WSJTx](https://wsjt.sourceforge.io/) running and connected to HAMRS directly to log straight into HAMRS.  I did use GridTracker for a while inbetween WSJTx and HAMRS, or in parallel - but I don't bother anymore.  Both as I don't need the graphical display - but I also push all of my logs from HAMRS to QRZ and then onwards.  

Once I have logs in HAMRS I can then hit the button to push them up to QRZ.  I have multiple logbooks in HAMRS (QTH Phone, QTH CW, QTH Digital, Portable) - but just the one big logbook on QRZ.  From QRZ (once setup) it's one click to push logs to the LOTW for additional QSO confirmation (beyond what QRZ does).  LOTW requires confirmation of your HAM qualification when signing up and you must generate a digital certificate using their tooling.  This provides an additional layer of authenticity to those QSOs and thus confirmations.  

As a last step every so often I export whatever new logs I have from QRZ (as it's one consolidated logbook) and import those logs to clublog and eQSL.  Clublog as I am participating in a few logner term contests tracked in there (run the year round), and eQSL as another method of sending eQSLs to folk. After paying a small fee I have created a eQSL card on eQSL that will get sent when someone confirms a QSO.  

There are a few steps to this overall - but everything beyond HAMRS can just be done when I feel like it (I usually do it once a week or so).  I would love to see HAMRS support direct upload to eQSL or clublog - and while I've asked for both it doesn't seem like there's too many asking for that functionality so my expectations aren't too high.  I don't think writing something to add to the mix of stuff I already have makes things any simpler either - but maybe that will change in the future.  

