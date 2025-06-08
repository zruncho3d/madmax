# The Story of MadMax

This started off with a discussion with Jon (from the awesome Proper Printing YT channel - check it out!) at OpenSauce 2023 (~June 2023).  Shortly after, I built a little desk toy to play with:

| ![](Images/Desk_Toy.jpg) | ![](Images/Desk_Toy_2.jpg) |
| --- | --- |

A Maxwell coupling is a special kind of coupling - [a kinematic coupling](https://en.wikipedia.org/wiki/Kinematic_coupling) - that effectively guarantees repeatable alignment, which makes it a great choice for systems which need to attach and detach a head frequently.  A Maxwell coupling uses balls and pins; read the [Wikipedia page](https://en.wikipedia.org/wiki/Kinematic_coupling) if you haven't already.

This toy is trying out multiple ideas: a magnetic-only Maxwell coupling (with no positive lock), as well as push-push latches as a dock mechanism.  Simple and fun... but there was a big Q: will the head stay on, or get flung off?

In the initial demonstrator, those M3 ballstuds (borrowed from a Kossel delta printer with magnetic-ball joints from a decade prior) are too big, obviously, and too heavy.  But man is it fun to play with!

I tried out M3s, M4, and M5 button-head screw variants. They all seemed fine, so I went with M3 for the weight savings and packaging ease.  A few N52 magnets with a small gap seemed to have plenty of hold.

Then, I moved to a demo that put the coupling on a modified [Boop](https://github.com/PrintersForAnts/Boop) carriage with pinned belt clips.  I had been testing the carriage for some time already and really liked the ease of use of pins, because when you're iterating on a carriage design, it shortens the iteration cycle.  When you don't know exactly what your design is going to be, this is the most important thing - speed of iteration.

Note - this drops into an existing carriage, replacing the vertical shorty MGN9 "Tap rail" on Boop.  It would never be a final design, but it enables you to get the next critical answer.

| ![](Images/Desk_Toy_3.jpg) | ![](Images/Desk_Toys.png) |
| --- | --- |

I couldn’t see a good way to make this with a top-facing rail, so I tried out a [front-facing gantry mod from richardjm](https://github.com/richardjm/voron-parts/tree/main/voron-0.1/Mgn9h), which had been in use to enable Boop for smaller V0 printers.

So, the next Q this helped answer: will the torque of the gantry suffice to pull it on and off?

I tried it... yes.  And you'd still have plenty of hold for the toolhead.  Running the numbers with my motors, it seemed like maybe 20 lbs of gantry motion force at full motor current, with only a few lbs needed for a solid toolhead hold for a V0-scale toolhead.

That was a sign that a toolchanger could happen, but I didn't like the push-push latches.  Sure, you can pack more heads densely in X, but you really want one big push-push latch, not 3; when 2/3 re-latch, that's bad.  Plus, they need a lot of travel to attach and detach.

Magnets work great, so I wanted to try the simplest dock design I could imagine - one that held magnetically in place, with keyslots:

| ![](Images/Early_Side_Mount.jpg) | ![](Images/Early_Side_Mount_2.jpg) |
| --- | --- |

The simplest design actually seemed to work - ferrous FHCS grabbed by tiny magnets.  Stuff like this is why I keep old unused plastic around!

Then around Nov 2023, it became clear that the toolchanger wasn't the most valuable thing to work on.  

Say you build a toolchanger with this... or really anything with two heads... how will you do nozzle alignment?  I knew that the pain of a TC for nozzle alignment would be shared with IDEX, DG (Dual Gantry), and other two-head printer types, and it was the core reason I had built those but never used them.  In fact, for [Double Dragon](https://github.com/zruncho3d/double-dragon) - a V0 IDEX (!), I used it for a grand total of two months, before it went back to its cave, because I feared the pain of manual vernier calibration prints.  For [Dueling Zero](https://github.com/zruncho3d/DuelingZero) I only used one head in practice.

Calibration is work.  Design is fun.  You can guess which one I, and most people, prefer.

That led to Nudge as a MadMax spinoff... spend 100+ hours to save a 10-minute calibration print :smile:.  Here's what it looks like, in the released form... on an early MadMax that almost nobody knew about.

![](Videos/Probing.gif)

If you're curious, check out the [Nudge repo](https://github.com/zruncho3d/nudge), which has its own design story, and lots of prototypes - a few of them shown below:

![](Images/prototypes.jpg)

Anyway, back to MadMax.  I wanted to test the attach/detach motion, which required an actual magnetic Maxwell.  Here we go:

![](Images/Early_Core.jpg)

Note that the balls are on the carriage and the pins on a plate, which attaches to each head.  The big design flaw this exposed is that you want the magnets higher-up, to better counteract the torque of the head.

I moved to a front dock, thinking it would be more secure; side docking can want to twist the dock itself as the head detaches.  In hindsight, this isn't a fundamental issue, just a reminder to go thicker.  With a front dock you can also mod an existing toolhead, which seemed like a nice benefit for a toolchanger conversion.  Here's how it looked:

| ![](Images/Front_Mount.jpg) | ![](Images/Front_Mount_2.jpg) |
| --- | --- |

OK, we can work with this.  A few versions, trying out different magnet placements:

| ![](Images/Front_Mount_Attached.jpg) | ![](Images/Front_Mount_Attached_2.jpg)  | ![](Images/Front_Mount_Attached_3.jpg) |
| --- | --- | --- |

What I didn't like was that when the head would pull away, it would separate from the plate, but then get pulled back in with a somewhat-loud clunk.  So I tried out a gentler attach and detach, with a magnetic-suspension "pusher plate" that would remove motion after detachment, as well as quiet it down:

![](Images/Front_Mount_Pusher_Plate.jpg)

Good enough for first attach/detach tests.

| ![](Images/Front_Mount_Pusher_Plate_Testbed.jpg) | ![](Images/Front_Mount_Both.jpg) |
| --- | --- |

Note the use of half a Dueling-X 2020 - a single gantry - facing the front, in a 2020 frame made with Rook frame parts, donated by Fabreeko (thanks!).

But I wanted a V0 toolchanger, just because it's kinda stupid and kinda great.  Really compact, and a great developer testbed.

![](Images/Front_Mount_Pusher_Plate_Testbed.jpg)

I wasn't fully happy with the front-facing gantry mod and figured I could do the XY joints in a single part and it would be stronger.  

Enter the next spinoff of MadMax: the [Vampire Bat](https://github.com/zruncho3d/vampire_bat) carriage, which paused MadMax, and was released in early 2024.  At that scale, extrusionless is fine!

![](Images/Vampire_Bat_Render.png)

But the plan all along was to merge the early carriage with its 3 screws, and turn that into a testable toolchanger.

Note here, an early prototype Vampire Bat gantry with single-piece XY joints, but a modified Vampire Bat carriage:

![](Images/Vampire_Bat_Clips.jpg)

The beauty of a pinned carriage is that you can switch out to new carriages quickly, without resetting belts, retensioning anything, or retesting anything.

I needed a way to do probing, and had been messing around with plastic for that, 'cuz it's fun...

![](Images/Poke_Below.png)

[Poke](https://github.com/zruncho3d/poke) - a single-piece flexure-based drop-in bed probe for V0-compatible heads - was gonna be the way to enable probing with a toolchanger head.  For awhile I used it and it worked on my green Tri-Zero which was becoming the testbed for MadMax:

| ![](Images/Poke_inside.jpg) | ![](Images/Poke_Inside_Plate.jpg) |
| --- | --- |

The next change was to flip the orientation.  A few thoughts drove this:
* 3 screws are cheaper for each head than 6 pins and easier to build.
* You want the largest Maxwell coupling area possible, for better stability.  Using the 3rd screw of a MiniSB mount at the top helps.

Here's the comparison.

![](Images/Flipped_2.jpg)

At this point, I didn't know whether to do a 90 degree orientation, like the PrusaXL and Daksh use, or a more traditional 120-degree orientation.

We need a real dock, though, for a V0.  I went with a simple, strong, blocky design.

| ![](Images/Side_Dock.jpg) | ![](Images/MiniSB_Dock.jpg) | ![](Images/Widebody.jpg) |
| --- | --- | --- |

I always thought the "Wideboy" MiniSB mod - with plates added to it - looked cool.  That gave the flat surface and known-good geometry for the FHCSes that go to the dock.

![](Images/Built.jpg)

But... it didn't all fit AND have space for the travel Nudge needed in the center.

So I moved to a toolhead from Kevinakasam called OmniBurner, and chopped the sides to enable the FHCS mount; at 54mm, vs ~58mm, I had the space needed to put a Nudge in front.

You can see the work-in-progress below, also with a first attempt at a Bricked toolhead style, where the toolhead board is in front of the extruder.  This pairs well with extruders that don't need much front space, like the PapLite extruder shown here in the center.

![](Images/Front_Heads.jpg)

Add some front shrouds...

![](Images/Ready_To_Go.jpg)

Now we have a complete toolchanger, with potentially automatic calibration, and can move to test prints!

![](Images/Cat_First_Print.jpg)

It's not impressive, but it's from the world's smallest, least-practical toolchanger, so I'll take it.

![](Images/First_Print.jpg)

It looks cool at night, accidentally; the two Huvud toolhead-board versions each had different lights, and the shrouds make the light more interesting!

| ![](Images/Night_Print.jpg) | ![](Images/Night_Print_Cat.jpg) |
| --- | --- |

Surprisingly, the prints had near-perfect calibration, out of the box, with only Nudge.

| ![](Images/Test_Print.jpg) | ![](Images/Test_Print_2.jpg) |
| --- | --- |

This is extremely good layer stacking.  The coupling is certainly not hurting print quality: the most important part, and largest unknown, seemed fine.  The seams are clean too.  But, all this was with a prime tower to catch drool, and you really want blockers and brushes to minimize drool while the heads move to the prime tower.

![](Images/Initial_Blockers.jpg)

This was the first attempt using silicone baking brushes, chopped down.  I didn't like that they blocked the view when you wanted a one-extruder print.

At this point (June 8), we have something worth printing, and the Closed Beta began for real, with the goal of getting more builds, evolving the parts, and figuring out whether this was even worth releasing.

![](Images/Beta1.png)

OpenSauce 2024 was a big motivator to get a real test print to share with Voron and YouTube folk.

![](Images/OpenSauce.jpg)

Seeing the Voron Phoenix IDEX in person, seeing a Prusa XL, seeing Jon's crazy dual gantry printer, talking to Voron Crew... it's all motivating stuff.

Excited, I went home and spent the night getting something more than a basic cylinder test.  Went to sleep late, after a failure partway through an alternating-layers Voron Cube print:

| ![](Images/Fail_1.jpg) | ![](Images/Fail_1_Zoom.jpg) |
| --- | --- |

I looked at the detached head:

![](Images/Fail_Why.jpg)

You see the issue?  Yeah, in a hot chamber (from my first long two-extruder print), all that heat in that tiny space meant that the plastic around the magnet relaxed, and it popped out.

So the next day at OpenSauce, I showed the coupling and asked everyone I saw - "how would you solve this?" - and got something like 20 unique answers, some hilariously impractical, and some straightforward and good. Answers ranged from Tom Sanladerer's suggestion of special metal-plastic glues, to using magnet wire, to putting a bigger magnet on one side.

![](Images/Voron_Booth.jpg)

BTW, Phoenix is HUGE.  This was before the rush of people.

That night, a quick fix with a drill, and we had a solution.  The print succeeded, and it was glorious.  Gemma-cat agrees.

| ![](Images/Cubes.jpg) | ![](Images/Cubes_Gemma.jpg) |
| --- | --- |

What was the change?

![](Images/Fix.jpg)

The critical improvement was FHCSes to hold the magnets by their edge chamfer.  This is a simple way to avoid glue and hold them in at higher temps, plus avoid any dependence on a specific printer, which affects the level of plastic grip.  It's just bad to rely on plastic grip alone, anyway.  It will inevitably fail in a hot chamber.

Lots of testing later from the beta team, and the focus had moved to long-term reliability and reducing probe force.  

The set screws holding in the wires - used for head detection through the plate, for the toolchanger firmware - would come loose with time.  Same issue as Poke... metal into plastic is bad in a hot chamber.

At this point, many of us in the beta were doing Maxwell probing, where the coupling itself is the probe sensor, as it slides up, and the pins and screw heads break their connections.  Surprisingly, you can get triple-zero probing here - 0.000x mm Std Dev - which is vastly better than needed.

But, that probing wasn't perfectly reliable over time.  There's a tradeoff which affects probing reliability.  If you increase the magnet force, potentially you get a better coupling, but potentially at the expense of higher probe forces, which may hurt repeatability.  Without numbers, it's all guesswork. That little gap also affects force, heavily.  What should it be?

The next MadMax spinoff was a load-cell-based magnet tester, which could be put into a printer to measure the drop-off in magnet forces, as the temp rises:

![](Images/Magnet_Tester.jpg)

In the tester, a motor turns a lead screw, which pulls on a magnet, and you watch the force drop off as the magnets pull away.  Look at the peak, and that's the magnet force.  You can measure magnet force with single-gram precision, up to multiple Kg, with only $12 of Amazon load cell parts (HX711 board), plus a Raspberry Pi and a few hundred lines of Python.

The tester justified the time investment.  It quantified the drop in force at chamber temps, and showed that no, we don't need higher-$$$, more-exotic Samarium Cobalt magnets here.  At our chamber temps (sub-70C), N52s are still stronger.

![](Diagrams/N52.png)

Don't over-index on the little dip; plastic bits in the tester probably started creeping loose around 64C, and the USB hub died.  Keep your consumer electronics out of the oven...

The tester was soon generalized to other purposes, like measuring the friction on various pin materials, with a little sled thing, weighted by a stepper:

![](Images/Tester_Pin_Friction.jpg)

I tested everything McMaster had in 1/8" rod: Steel, PTFE, ABS, PP, POM, Nylon, Graphite, and Greased Metal.

![](Images/Tested_Materials.jpg)

Here's an example graph:

![](Diagrams/Magnet_Tester_Data.png)

... and that's why we spec Acetal (POM).  Low friction, high durability.  Less probe force than metal pins; not as soft as Teflon (PTFE), which deforms quickly from magnet forces.

I could even measure magnet forces from probing, to quantify the effect of gap changes and other things.  That required some upgrades to the tester, to move from flexy V-wheels on V-Slot extrusions, to parallel MGN9 rails:

| ![](Images/Rollers_To_Rails.jpg) | ![](Images/Probe_Tester.jpg) |
| --- | --- |

I was so happy when I could "call a shot" - take measured magnet force data, combine it with measured friction coefficients, and predict a probing force change.  This helps you consider design tradeoffs, like "head grip" vs probing force.  It's amazing when the model matches the measured reality.  Then, you truly understand what you have, and how to tune it.

By this release, SpeedClips where a thing too - yet another spinoff:

![](Images/SpeedClips_First.jpg)

SpeedClips open up the clip aperture, so you can adjust the belt position quickly.  They're awesome.

All this knowledge folded into a Beta2 release, with a completely new CAD, which uses Fusion configurations to enable 90 and 120 degree versions, as well as MGN9 and MGN12 variants, in one file.

![](Images/Beta2.png)

Relative to beta1, the main changes were:
* MGN12 support
* 120 degree "official" support
* vastly better wire routing in the plate (though the plate!)
* locking thumbscrew support for IS testing
* optional carriage magnet locking screws to prevent heat-cycle-induced pullout
* nuts/screws instead of set screws on plate
* bar option instead of wires and set screws on carriage
...and a bajillion small dimension changes.

Video here: https://youtu.be/EqUv1yK-KEs

It was all shown for the first time, in person, at Reno VICE in October 2024, as part of the Pacific Ant Fleet's visit (my cadre of small printers). Note that Dueling Zero, on the right, is using the MadMax core here.  For over a year, I've been dogfooding this thing.

![](Images/VICE.jpg)

More beta members, more lessons: connection reliability, build speed, and print quality are the big focus areas, still, which led to Beta3 in October 2024.

This one had a complete CAD redo for maintainability, plus extra sizes added (MGN12 w/ 9mm belts), and eliminated formed threads.

At this point, it becomes clearly that this is not that crazy.  Lots of people are succeeding with builds and impressive prints.
Some surprising benefits from living with it for a year:

* Maintenance ease - grab a head, inspect it, and put it back, no tools needed.
* No tuning vs MMUs - no tip tuning, no distance/speed tuning.  Just offset calcs, but those are automatic with Nudge.
* Actually pretty cheap with cheap hotends (TZ-V6 is $20, EBB is sub-$20) - can cost less than an MMU setup.
* Mainline Klipper has benefits.

Still, there's an issue... creep on connections, especially on the plate, especially in a hot chamber.  If you tighten a screw hard, the plastic will relax at high temps, causing a loosened connection.  Then to "fix" it, you tighten it harder, creating a frustrating downward spiral.  To avoid this, in early 2025, Beta4 moved to heatsets on the plate, with ring terminals and crimps, and clearance for those.  A small change, but it eliminates creep worries on the plate.  

At this point, if you're still reading, learn more about the final design from the [DESIGN.md](DESIGN.md) section!
