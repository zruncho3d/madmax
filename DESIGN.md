# Design

**This page tries to explain goals, requirements, metrics, non-goals, and design choices in that direction.**

*Hopefully it saves you some wasted time, or at least, helps you understand why things are the way they are here, so you can better choose whether this project is right for you.*

No design is best, but a good design is one that understands what its goals and constraints are - then, achieves them under budget, while delivering a good experience for the target audience.

**The audience for MadMax is NOT everyone.**  We're just not there yet.

It’s for leading edge, tip-of-the-spear types.

But, no single step is hard! If you can build and configure a Voron, you can do the MadMax steps too.

What we’ve tried to achieve here is *not* to fit every toolhead or printer, but to be the simplest on-ramp to adding a second toolhead possible, and fit most toolheads and printers with a single common design.

## Goals:
* Enable high-quality multi-toolhead printing, for as many printers as possible, at reasonable price

## Requirements: “Must be:” stuff:
* **Easily sourced**: ideally all COTS stuff; no rail grinding or cutting, minimal electronics per head, if possible.
* **Safe**: crash detection is critical
* **Prints well**: no ringing, good IS
* **Tolerant to misalignment**: ideally at least 0.5mm of alignment inaccuracy
* **Performs**: ideally “weight neutral” or no more than 10% added head weight relative to other options.
* **Versatile**: support a wide range of printers, with as much available travel as possible
* **Fast to convert**: minimize wiring changes needed; ideally, sub-1 hr.  Can’t require full conversion like Pandora.

## Metrics: “Optimize for:”
* Cost: $100ish, or as low as possible, for the MadMax-specific parts and second head.
* Fast toolchanges: sub-second (!) target, but 4s is plenty fast, in practice.
* Minimal design work
* Ideally, enable multiple unchanged or minimally changed toolheads from the V0 ecosystem
* Ideally, conversion possible without having to reprint the first toolhead
* Ideally, enable X carriages (or similar) that already exist, especially the Pin-in-Tube Boop carriage

## Not goals:
* Any particular wiring layout; second umbilical for the shuttle is OK (for now) - maybe simplifies some startup stuff
* Support for full-size Voron toolheads (not that it won’t work, but you can fit more smaller toolheads in a fixed X length, and I haven’t made any to test on)

## Choices

For the design that emerged.. below are some interesting parts/choices/features/attributes, and discussion around them.  Yes, it’s a lot.

#### No glue, no tape, no epoxy: mechanical fastening only.
This isn’t trivial!   

You have to get the dimensions right to do press fits, like those used by the magnets, when every printer is slightly different.

We tried different sizes and magnet shapes, with a press fit.

How do you even do press fits when you want to use cylindrical magnets?

Solution: just the tip.  

#### Reliable metal connections with no special parts
“Metal sandwich construction” for wires, plus crimp terminals on the plate.

Advantage over crimp terminals: removes a part, tight packaging, can adjust wire length more easily this way.

Plastic deforms over time.  Originally we had set screws from the side.  It worked but not for long, in a heated chamber.  And they could strip.  Then we went to wires squeezed wires, but the connections would get loose due to creep.

Now, layer lines all aligned, and in compression; can’t split the layers by forming the threads.

There are no formed threads here anymore.

These have problems in a chamber, over time.  Heat cycles cause expansion and contraction, and then the screws loosen, and the electrical connection becomes flaky.  I’d see this after just a few print cycles!  Could tighten, but it’d come back eventually. It’s a fundamental deficiency; the metal expands more than the plastic, so inevitably it gets loose.

#### Easy Printing w/no supports needed and no overhangs, just small bridges
Show examples of complex multi-layer bridging.

Those 4-layer bridges on the plate and carriage are the most complex bridges I’ve ever done.

#### CoM/CoF alignment
Largest change here, from beta2 to beta3, required a lot of rework; shifted just about the lowest possible, without removing MSB as a possible toolhead.

Show examples and IS tester jig to show the effect of shifting CoG and alignment.

#### Clean airflow
Also part of beta2→ beta3 and many changes
Multiple issues; hotend clogs possible for cooling-deficient hotends like Dragon HF, but also components nearby heat up more and get softer.  Trying not to require exotic filaments for a long-term functional design here.

#### Pins + Screws Maxwell coupling
This is the core of the project and received the most attention and testing.

120 degree vs 90 degree: Not an obvious choice.  Prusa XL and Daksh use 90 degree - easier to machine and design.  Kept both and compared them.  Couldn’t see a difference with data.  120 is symmetric and enables easier connection and tighter package.

Note that CAD has a twist too, but wasn’t sure how to make use of that on the plate side.

BHCS, not acorn nuts

Lighter, smaller, won’t BUT need smooth ones, or you’ll see high friction effects.

Acorn nuts can flake and deform with the thin chrome upper.

#### “The probe is the coupling, and more”

List all functions…

#### As large as possible, but no larger

Can’t really go larger; MiniSB third hole and two front holes, combined with wanting the space to screw to bottom of the cowling on both DB8 and MSB, is what drives the dimensions.  Can absolutely go taller and wider for more stability, if you change those assumptions.  

#### Magnets tested with magnet tester
Magnet Force Data

Magnet configurations matter!  Examples + data.

Magnet materials matter!

Magnet qualities matter!

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
