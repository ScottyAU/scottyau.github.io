---
layout: post
title:  "I'm on a boat - Part 1"
date:   2014-09-28 21:18:00 +1000
tags:   Boating, Mechanics, Repair
---

So September has seen a bit of a change, in that instead of spending the little bit of time I get at the bench, it's been spent outside doing a bit of work on the boat getting it ready for a summer on the water!  The following happened over the last 3 weekends, and a little bit here and there during the weeks in between.  It was all kind of going on at the same time - but i've written it out as if it was one after the other.

We inherited the boat from my wife's granddad.  It's a fibre glass runabout with a 1985 Johnson V4 90hp oil injected two stroke.  The Johnson was one of the first models that used a Variable Rate Oiling or VRO pump.  These VRO pumps are a real sticking point on the internet and at the jetty alike.  People seem to give them a real bash for being unreliable and causing an outboard to have running problems or worse still - kill the outboard altogether (due to lack of oil).

We've only had the boat for a couple of summers, but it's been running without issue for 29 years.  I'm reliably informed my wife's granddad used the boat more than just about anything else. It's a pretty simple principal - the pump runs off pulses on the bottom of the crank case.  It mixes in petrol and a variable amount of oil based on the pulse output of the engine and pumps that mixture into the engine.  One of the best resources on VRO pumps is [this link](http://continuouswave.com/whaler/reference/VRO.html).

The pumps have changed a little over the years.  As this outboard was one of the first with a VRO - the pump has no electronics to measure and subsequently alarm when the oiling side of the pump fails.  Johnson also introduced a pulse limiter to use on the output of the crank case which runs the pump - to stop any damage to the pump from over pulsing (think back fires etc).

So with that context, I went outside to pull the cowl off the outboard and give it a run to see where things were at heading into summer.  There were 4 things that I noticed straight away:

 * The straps on the bimini covers had all broken
 * The hose from the fuel tank to the outboard had gone hard and looked like it might crack
 * The cable ties holding the remote control arm together had broken
 * The temp buzzer was on - before I even started the engine for the first time (this has been an intermittent issue since before we got the boat)

I metered the resistance on one of the temp senders while still connected (there are two) and it was pretty close to zero - even though the motor was dead cold.  Either one of the senders was dead or there was a wiring issue.  I parked this one here (knowing that the motor wasn't overheating), and figured I'd come back to it once the engine was running.  It's been one of those niggling issues that I've been meaning to fix since we got the boat.  I headed down to the shops and got some replacement  bimini straps, a new fuel hose and filled the fuel tank.

I came home and hooked up the new hose, pulled the battery off charge and connected it up.  With the muffs on and the hose running I cranked her over.  Noting that she hadn't been started in somewhere around 4 to 5 months (amazing where time goes when you become a Dad), she started pretty well after a little bit of cranking combined with some choke.

Once running she seemed ok - until I had a closer look and noticed fuel leaking from the VRO pump.  Bummer.  Most complaints about VRO pumps all revolve around the oiling part of the pump not working 100% or failing altogether.  My VRO though was leaking fuel.  It was still pumping fuel and oil just fine - with the engine running well.  Having a closer look at the VRO, it was quite obvious that the leak wasn't new, and someone had previously had a go at sealing it up:

![Im on a boat 1 1](/images/Im on a boat 1 1.jpg)

Unfortunately the pump housing is plastic.  If it was metal you'd just be looking for a seal kit to rebuild the pump, but as you can see in the photo above the plastic housing of the pump is cracked.  So there's no chance of fixing it - someone's already tried that.  

I did a bunch of looking and ringing around.  As I mentioned this engine is almost 30 years old now and the VRO pumps have changed a little bit over time.  I needed to figure out what part number I was actually chasing.  One of the best sites I found was [this one](http://www.marineengine.com/parts/parts.html).  You can find a part on your outboard and it will show you any superseded part number when you look the part up.  Awesome.

Turns out a replacement VRO pump is somewhere around $600-$700.  No.  Not happening.  

A few places did sell replacement after market pumps that are just fuel pumps for about $180.  This seems to be what everyone who dislikes VRO's says to do.  Disconnect the oil tank and just premix the fuel with oil.  Even though this would mean a brand new pump, I didn't overly want to do this so I parked this option as a backup.

I then rang a few boat wreckers, and managed to find a replacement VRO for $165.  Much better.   However the guy at the wreckers seemed strongly against VROs in general.  His choice.  The one thing he did say was I needed to bring the old pump in to match it up.  While the various versions of the VRO pumps over the years are pretty much the same thing internally, the angle of some of the hose connectors does change depending on the outboard.  So out I went to pull the existing VRO off.  In doing so I noticed most of the connecting hoses were pretty hard and ready to be replaced.  

Off to the wreckers to get the pump, and then the shops to get some replacement fuel hose and hose clamps.  

It was pretty easy to put the new (old) pump on with some new sections of fuel hose and hose clamps.  I primed the oil and fuel lines and cranked her over again.  

She started easily and ran really well - without leaks!  Winner.

Next stop was the temperature warning buzzer.  As mentioned above it's been an intermittent issue since before we inherited the boat, it was time to figure it out and fix it.  It only came on sometimes, but the engine never overheated.  I'd played with a couple of connections that appeared to sometimes make a difference, so I just put it down to a wiring problem.  At this point I should note the electronics on this outboard are very basic.  After a bit of reading online, I learnt the following:
The buzzer sounds when the temp circuit grounds
There are two temp senders - one in each head
Any VRO oil warning circuitry is connected into the temp circuit in parallel
Lots of posts online about people finding shorts somewhere in the wiring causing the problem
With all this new knowledge in mind and a meter in hand it was time to track down the gremlin once and for all.  I started out with each temp sender individually.  Both passed.  Stupidly high resistance when cold, and it started to drop when they warmed up. 

Noting what I said earlier about my VRO pump being 1st generation and not having any electrics for warning circuitry, I was almost ready to rule this point out.  That was until I started tracing the wiring from the outboard back to the remote control where the warning buzzer is.  I noticed a wire coming in from the oil tank.  Confirming online, there is a float in the remote oil tank that earths out when the oil gets low to sound a "low oil" alarm.  I disconnected this guy from the circuit and the buzzer stopped.  Bingo.  Metering it the resistance was almost non existent.  Problem found.  

I set about pulling the oil pickup/float out of the oil tank (it's all one piece).  I started having a look to see if it was stuck/could be fixed and it basically fell apart in my hands.  Awesome.

It was a mix of plastic and metal - and it was busted.  Not just the float, but the pick up too.

I headed back online to look for a replacement pickup/float.  At least $200.  Did I just do the wrong thing getting a new VRO and not just replacing it with a straight fuel pump and premixing?

I checked eBay, and BAM.  A full (that's right full - not just the pickup) remote oil kit (old new stock), about 20 minutes for home - for $15!!!  I couldn't get down there to pick it up quick enough:

![Im on a boat 1 2](/images/Im on a boat 1 2.jpg)

Fitting this guy up was pretty straight forward.  The hose and two wires needed to be trimmed as they were both massively too long at factory length.  Once hooked up - I filled it with some nice new marine 2 stroke oil (I primed the oil line as best I could when hooking it up) and turned the key to on - no warning buzzer!  So I started the outboard and again - no buzzer.  She runs pretty smooth. 

Buzzer issue solved.

I should mention that somewhere in there while trying to find the problem with the buzzer - I blew the main fuse on the motor.  This wouldn't have been much of an issue (after all - what are fuses for?) but the holder took a very weird size cylinder fuse that I couldn't get in the local SuperCheap or Autobarn.  That combined with the wires on either end being worse for ware, I simply bought a new standard size blade fuze holder and put it in.  Another problem (introduced while fixing the outboard) fixed.

So last problem - the remote control.  It was broken and held together with cable ties when we got it.  When I was at the wreckers, I mentioned it to the bloke there and he knew straight away what I was talking about.  The actual throttle arm is metal, so its fine, but there is a plastic piece on one side of the arm that holds the tilt switch at the top.  This piece just snaps off after a while due to it's design.  Given this - he said second hand non-broken replacements don't exist and that I'd have to get one new.  $70.  I told him I'd think about it and went home and used some duct tape:

![Im on a boat 1 3](/images/Im on a boat 1 3.jpg)

One other part that I was keen to get was the pulse limiter that is mentioned in the external VRO link:  

"Since the VRO depends on crankcase pulses to operate, it is susceptible to backfires from a lean running cylinder or an out of tune engine. If your motor is older than a 1993, make sure it has the blue colored pulse limiter to protect the air motor and the check valves in the pump. Follow the pulse line from the VRO to the engine block and look for a hex shaped fitting threaded into the crankcase. If it has a black face on it, replace it with a blue style (OMC P/N 435009)."

No surprise that mine didn't have the blue limiter installed.  I wanted to make sure I put one of these on since I'd just spent the time and money replacing the VRO pump.  Knowing that I needed the pulse limiter and a replacement plastic arm for the remote control I got hunting online again.  I ended up going with [this place](http://www.huntsmarine.com.au/) based out of Sydney.  They have an online parts quoting form and once submitted Paul responded promptly to clarify my order, and that was that.  The prices with shipping were better than I got phoning around in locally too.  $54 for the pulse limiter and $32 for the plastic arm - winner!

Once the parts arrived I set about installing both.   The pulse limiter install I didn't really get a decent picture of (it's hard when your hands are covered in grease).  I did get a couple of pics of the remote control though (white part is metal, black part is plastic):

![Im on a boat 1 4](/images/Im on a boat 1 4.jpg)

![Im on a boat 1 5](/images/Im on a boat 1 5.jpg)

All done.  I've pumped up the tyres on the trailer and she's good to go.  We've got a long weekend coming up - so fingers crossed I should be able to get some time on the water to put the old girl through her paces.  Bring on Summer!