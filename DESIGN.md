# Design

**This page tries to explain goals, requirements, metrics, non-goals, and design choices.**

*Hopefully it saves you some wasted time, or at least, helps you understand why things are the way they are here, so you can better choose whether this project is right for you.*

No design is best, but a *good* design is one that understands what its goals and constraints are - then, achieves them under-budget, while delivering a good experience for the target audience.

**The audience for MadMax is NOT everyone.**  We're just not there yet.

It’s for leading edge, tip-of-the-spear types.

But, no single step is hard! If you can build and configure a Voron, you can do the MadMax steps too.

What we’ve tried to achieve here is *not* to fit every toolhead or printer, but to be the simplest on-ramp to adding a second toolhead possible, and fit most toolheads and printers with a single common design, so that ports happen from the community.

## Goals
* Enable high-quality multi-toolhead printing, for as many printers as possible, at reasonable price

## Requirements

“Must be:” stuff:
* **Easily sourced**: ideally all COTS stuff; no rail grinding or cutting, minimal electronics per head, if possible.
* **Safe**: crash detection is critical.
* **Prints well**: with no ringing, and good resonance testing.
* **Tolerant to misalignment**: ideally at least 0.5mm of alignment inaccuracy allowed, and ideally beyond.
* **Performs**: ideally “weight neutral” or no more than 10% added head weight relative to other options.
* **Versatile**: support a wide range of printers, with as much available travel as possible
* **Fast to convert**: minimize wiring changes needed; ideally, sub-1 hr.

## Metrics

“Optimize for:” stuff:
* Cost: $100ish, or as low as possible, for the MadMax-specific parts and second head.
* Fast toolchanges: sub-second (!) target, but 4s is plenty fast, in practice.
* Minimal design work
* Ideally, enable multiple unchanged or minimally changed toolheads from the V0 ecosystem
* Ideally, conversion possible without having to reprint the first toolhead
* Ideally, enable multiple non-V0-ecosystem toolheads, too

## Not goals
* Any particular wiring layout; second umbilical for the shuttle is OK (for now) - maybe simplifies some startup stuff
* Support for full-size Voron toolheads
* Initial support for more than two heads

## Choices

For the design that emerged.. below are some interesting parts/choices/features/attributes, and discussion around them.  Yes, it’s a lot.

#### No glue, no tape, no epoxy: mechanical fastening only.
This isn’t trivial!   

You have to get the dimensions right to do press fits, like those used by the magnets, when every printer is slightly different.

We tried different sizes and magnet shapes, with a press fit, and a survey of builders.  How do you even do press fits when you want to use cylindrical magnets?  You test and find a happy medium.

In one early test in a hot chamber a magnet escaped, which motivated the magnet-retention screws, solved by using just the tip of a screw.

#### Reliable metal connections with no special parts
“Metal sandwich construction” for carriage wires, plus crimp terminals on the plate.

Plastic deforms over time.  Originally we had set screws from the side.  It worked but not for long, in a heated chamber.  And they could strip.  Then we went to wires squeezing wires, but the connections would get loose due to creep.

Heat cycles cause expansion and contraction, and then the screws loosen, and the electrical connection becomes flaky.  I’d see this after just a few print cycles!  Could tighten, but it’d come back eventually. It’s a fundamental deficiency; the metal expands more than the plastic, so inevitably it gets loose.

Now, layer lines are all aligned, and screws are in compression; can’t split the layers by forming the threads.  There are no formed threads in the parts anymore.

What we have on the plate (which sees the most heat) is solid - metal touches metal.

The carriage has it a bit easier for now, heat-wise, and seems OK after an initial retightening.

#### Easy Printing w/no supports needed and no overhangs, just small bridges

The 4-layer bridges on the carriage are the most complex bridges I’ve ever done.  They're not hard; they just take time to ensure clean prints.  The plate, near the crimp cutouts, also has some complex bridge work.

TODO: show picture of complex bridges.

#### CoM/CoF alignment

Largest change here, from beta2 to beta3, required a lot of rework; shifted just about the lowest possible, without removing MSB as a possible toolhead.

TODO: Show examples and IS tester jig to show the effect of shifting CoG and alignment.

#### Clean airflow
Also part of beta2→beta3 and many other related changes.

Multiple issues; hotend clogs are possible for cooling-deficient hotends like Dragon HF, but also components nearby heat up more and get softer.  We're trying not to require exotic filaments for a long-term functional design here.

Shifting the head downwards enabled a much more unrestricted path for hotend air.

#### Pins + Screws Maxwell coupling
This is the core of the project and received the most attention and testing.

120 degree vs 90 degree is not an obvious choice.  Prusa XL and Daksh use 90 degree, as it's easier to machine and design.  We kept both and compared them with beta2, but couldn’t see any difference with data.  120 is symmetric and enables easier connection and tighter package, so it became the one.

Note that CAD has a twist too, so that you can preload the Maxwell coupling against gravity somewhat, but I wasn’t sure how to make use of that on the plate side.

Uses BHCSes, not acorn nuts; acorn nuts can flake and deform with the thin chrome upper.

#### “The probe is the coupling, and more”

TODO: List all functions of the maxwell probe…

#### As large as possible, but no larger, for the coupling
The coupling can’t really go larger, without major changes; the MiniSB third hole and two front holes, combined with wanting the space to screw to bottom of the cowling on both DB8 and MSB, is what drives the dimensions.  One can absolutely go taller and wider for more stability, if you change those assumptions, but this width seems OK for now.  Yes, it's strictly better to go wider and taller.

#### Magnets tested with magnet tester
TODO: Magnet Force Data

Magnet configurations matter!  Examples + data.

TODO: Magnet materials matter!

TODO: Magnet qualities matter!

#### Probe Force tested
Material Friction Force Data

Note issues with repeatability, including at higher temps - never felt 100%

Probably actually abundance of caution stuff.. Likely due to set screws loosening

Friction effects from screws

Friction effects from materials - shown data

#### Special hole sizes for improved stability.  Not just 3.3mm holes
Importance of eliminating unwanted motion.

#### Parametric CAD
Show example

#### Configured Fusion360 CAD
Show parameters.  Much harder, because you have to solve the puzzle of how to enable/disable features which are only possible for one scale.  Benefit is that new sizes become easier.  

#### Reliability Testing
Many many tests, done with aggression
Some light plastic wear seen; no failures here.
One attachment failure from magnet pullout; addressed now

#### Actual print testing is king!
Note from Z about how interesting this has been, with tangents

#### Spinoffs aplenty

Did you know?  Nudge and VB and OmniBrick and DragonBrick and the universal tester are all spinoffs from this long journey.
