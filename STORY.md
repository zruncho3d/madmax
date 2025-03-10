# The Story of MadMax

TODO: spend the time to really fill this in, with pictures and videos from the archives.

This started as a desk toy to play around with push-push latches and Maxwell couplings, following a chat with Jon at Proper Printing at OpenSauce 2023 (~June 2023).

TODO: add video/picture of desk toy.

This is trying out multiple ideas: a magnetic-only Maxwell coupling (with no positive lock), as well as push-push latches as a dock mechanism.   Huge unknowns, but a simple build... will the head stay on, or get flung off?

TODO: What is a Maxwell coupling?  Add details for a maxwell coupling vs other type of coupling, Wikipedia link.

In the initial demonstrator, those spheres are too big, obviously, and too heavy.  But man is it fun to play with!

I tried out m3s, m4, and m5s.  They all seemed fine.  So let’s try M3 BHCS for weight and packaging.

Then, moved to a demo with a maxwell coupling, to a modified Boop coupling.

TODO: add pic.

Will the torque of the gantry suffice to pull it on and off?

Tried it... yes.  And you'd still have plenty of hold.

I couldn’t see a good way to make this with a top-facing rail, so I tried out the richardjm gantry, which had been in use to enable Boop on F0, but I wanted a test gantry to try it out.

Did Nudge end of 2023… knew that the pain of a TC for nozzle alignment would be common with IDEX, DG, and it was the core reason I had built those but never did weekly or even monthly prints that would use both heads.  In fact, for Double Dragon, I used it for a grand total of two months, before it went back to its cave, because I feared the pain of manual vernier calibration print.

Then, did and released Nudge!  Tons of prototypes.  MadMax came first, but was on hold.

Mention front-facing and “blocking the view”.

Long ago, Hector at Fabreeko sponsored a Rook kit and some rails and magnets and bearings, and I added to that to build a DX-2020.  This was perfect for this with an MGN9H gantry.  Could do tests!

But my real printers are small…. Enter and explain Vampire Bat which emerged from wanting a V0-scale toolchanger, with a front-facing gantry.  Released that in early 2024.  At that scale, extrusionless is fine.  

[Add when it gets the temp name of MadMax and why]

Beta1 - more people to build

Mention OpenSauce 2024 as a motivator.

Showed off the coupling the first day.  Went home, printed, but it failed when a magnet pulled out.

Next day, went back, and told 20 people about the problem.  Got 20+ different ideas…

Beta2 and changes

Mention realizing that brickifying is a general thing and works well.

FHCSs and locking the magnets mechanically.

Lots of reliability testing, including in Dueling, which revealed lots of issues - same thing with Poke - metal into plastic is bad in a hot chamber.

Beta3 and changes; complete CAD redo for maintability, plus extra sizes.

Becomes clearly that this is not that crazy.  Surprising benefits:

* Maintenance ease
* No tuning vs MMUs - no tip tuning, no distance/speed tuning.  Just offset calcs, but those are automatic with Nudge.
* Actually pretty cheap with cheap hotends (TZ-V6 is $20, EBB is sub-$20) - can cost less than a toolchanger setup.
* Mainline Klipper has benefits.

If any of that was interesting, then move on to the DESIGN section, which explains a lot of this in more detail, and shows the choices that emerged.

[pic]

Beta4 and going broader.. change to heatsets as a fix for the plate connection reliability issues.