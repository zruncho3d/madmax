## MadMax - the crazy-simple toolchanger *conversion* for your CoreXY printer

Enable multi-material printing *on the printer you already own* - with low cost, low effort, low filament waste, and fast multi-material switching.

TODO: "Hero render" - Dramatic-lighting render of the core.

| ![gif](*.gif) | ![gif](*.gif) | ![gif](*.gif) |
| --- | --- | --- |
| Toolchanging | Printing | Probing (with Nudge) |

TODO: table with GIFs covering the main steps - ideally all perfect loops

**MadMax is currently in active beta**, with over 10 builds doing reliable two-head prints:  

TODO: print samples/sample printer build (probably a collage for easier formatting?)  One option is to have a picture, a link to details for all beta builds, an interesting Voron cube, and something else.

Learn more from videos:
* [Canuck Creator interviews Ambrosia](https://www.youtube.com/watch?v=dB9FqNF6or0&t=164s)  - with MadMax Trident
* Fast toolchanges and motion with Andrew's build
* Core Build
* [Speedclips.... they're real, and they're spectacular](https://www.youtube.com/watch?v=UsWV_GbRdjc)
* Selecting a Toolhead
* TODO: link more printer and print videos

**This is an advanced mod**: you must be comfortable with modifying Klipper configs and debugging related error messages.

**This project is in beta**: parts are well-tested/well-trusted and docs are nearly complete, but expect changes to parts and expect minor gaps in docs.  

Earlier in a project is where your efforts will have the highest impact, so now's the time to jump onboard.

## New parts concepts, yet easily sourced

| (pic) | (pic) | (pic) | (pic) |
| --- | --- | --- | --- |
| Carriage | Plate | Clip | Example Dock |

TODO: add isometric/flat renders for the above.

A combination of new parts makes it possible:
* **Core:** A new “pins and screws” magnetic [Maxwell](https://en.wikipedia.org/wiki/Kinematic_coupling) coupling enables head attach/detach, head detection, AND probing.  
  * Yes, you heard that correctly!   The core carriage+plate mechanism _is_ the probe, if you want.  The Maxwell coupling is engineered to slide in place with low friction, enabling high-quality probing up there with Tap and Boop, but lighter, lower-cost, and with more stable motion.  Here's a sample probe run:
  `probe accuracy results: ... range 0.002031,... standard deviation 0.000548`.  Not bad!  In fact, you can use the core on non-toolchangers to get easier maintenance.
* **Clips:** The new SpeedClips belt clips are the fastest belt attachment mechanism around, plus enable repeatable tensioning.
* **Docks:** The docks use ferrous flat-head screws and magnets, in a simple keyslot.  Light and low-cost.

All parts use easily-available and sourced-anywhere-globally parts, like pins, screws, and magnets.  You may already have everything you need to build this in your toolbox!

So, what's the catch?
* Some lost build volume when printing with two heads. This is inherent in all toolchangers, but for single-head prints you can detach the second head in seconds, to restore nearly 100% of the original build volume.  TODO: explain with its own page.
* No positive lock on the toolhead - only a magnetic one. In practice, this works fine, and means that no complex locking mechanism or motors are needed.  It's safe; should the head detach for any reason, the firmware immediately safes the printer, just like with any other fault.

That’s about it.  It’s a more straightforward mod than you might think.

## Enable serious new capabilities

This mod is for those who want a more capable printer.

The surprise is that you can enable *many* new capabilities, with only about $100, one night of printing, one night of building, and one night of configuration and tuning:

| Use case | Multiple colors in one print  | Multiple material types in one print: flex + hard | Full-contact supports | Tap replacement |
| --- | --- | --- | --- | --- |
| Example | Benchy?  Two-color voron cube? | Overmolded grip screwdriver? | What to put here? | Pic showing vs Tap on scale |
| Benefits |  No adhesion issues/bleed vs MMU; vastly reduced waste and delay, multiple TPU colors | No mixing/adhesion issues vs MMU, vastly reduced waste and delay | Clean support interfaces, with no mixing issues with an MMU | Lighter weight and better IS results, plus detach head for easy maintenance |

Unlike toolchanger designs that require up/down docking motion, MadMax supports static-gantry printers (like Voron Trident), *without* the added cost/complexity of a [liftbar](https://github.com/viesturz/tapchanger/blob/main/Dock/Liftbar/Liftbar.md).  XY-only toolchanges are lightning-fast, which can speed up overall print time, improve multi-extruder print quality, simplify print tuning, and reduce priming waste.

TODO: Add print-sample pictures.  Show examples with weight/time with 100% vs stock, to motivate the choice vs MMU.

## An entire toolchanger ecosystem

MadMax is more than just the core and dock interfaces; already, **it is an entire toolchanger ecosystem** covering most common [Voron](https://vorondesign.com/) and [Printers for Ants](https://3dprintersforants.com/) printers, plus many open-source toolheads and extruders.  The main requirement is a front-facing MGN9H or MGN12H linear rail and XY head motion, so bed slingers are out.  Both 6mm and 9mm belt sizes are supported.

If you don’t see your printer in the list below, adding it tends to be straightforward.

TODO: "MadMax Toolchanger Ecosystem" table - image showing real printers with this (and links), mentioning full compatibilty.
Below: 2x+ [MGN9H, MGN12H], 3x+ [MSB/OB, DB/AH, XOL/A4T], 4+ [OB, DB, A4T, XOL, ..] on 8+ printers.  

TODO: link to full-detail compatibility matrix.

## Easy to print, build, and configure

All parts are easy and fast to print, with no large overhangs, large bridges, and supports included.  Here's a full plate for a DragonBrick Trident conversion:

TODO: show all parts needed for a two-head setup, in one image

The entire conversion can be done in an evening, as covered by instructional videos.  No individual steps are hard.

TODO: Video: building MadMax: core build
TODO: Video: building MadMax: plate build
TODO: Video: building MadMax: toolhead choices
TODO: Video: building MadMax: dock samples

Sample Klipper configuration is available in this repo, for [Viesturz' klipper-toolchanger](https://github.com/viesturz/klipper-toolchanger), but [TypQxQ's KTC2](https://github.com/TypQxQ/KTC) and [Bikin Toolchanger](https://github.com/Bikin-Creative/Lineux-Toolchanger/tree/main/Klipper) are also potential options.

TODO: Video: Configuring MadMax with klipper-toolchanger (show Klipper config)

Calibration is fully automated (using [Nudge](https://github.com/zruncho3d/nudge)), can run on every print, and includes head crash detection for safety.

TODO: Video: Initial MadMax calibration (XY positions, reliability)
TODO: Video: head crash detection for safety!

Every-print auto-calibration looks like this:

TODO: Video: Auto-calibration between nozzles

This is a big deal for the overall experience of a toolchanger, because it removes the main source of pain relative to automated filament changers.  You can change hotends or adjust the mount - things which can affect offset calibration - and there’s no work to do, because calibration is automatic.  Plus, any differences in offsets due to temperature or changes to the positions of the heads or the frame are automatically accounted for, by probing at the operating temp.

### Key features
* Support for a wide range of printers and toolheads
* Fast toolhead changing for faster, better multi-extruder prints
* Bonus Maxwell-coupling-driven nozzle probing (!) - not a requirement to use
* Toolhead failure detection without extra parts
* Bonus pragmatic features:
 * Pinned carriage enables reproducible retensioning
 * Fully reversible conversion process
 * Documented and simplified steps for toolchanger setup with Klipper
 * Reliable: no glue, no servos to fail, no slow Z motion on toolhead changes.

## What's here?
- #### [Getting Started](GETTING_STARTED.md) - select a printer, toolhead, and extruder, amongst choices
- #### [Instructions](INSTRUCTIONS.md) - print and build steps
- #### [Configuration](CONFIGURATION.md) - Klipper config and calibration
- #### [Story](STORY.md) - how and why this project came to be
- #### [Design](DESIGN.md) - notes on design choices; especially useful for doing ports
- #### [FAQ](FAQ.md) - covers questions you may have; worth a skim
- #### [Troubleshooting](TROUBLESHOOTING.md) - steps to diagnose the most-common errors

## Support the creator
Like what you see?  [Buy me a coffee](https://ko-fi.com/zruncho3d) to show the love and enable future mods and content - stuff like [F0](https://github.com/zruncho3d/f-zero), [T0](https://github.com/zruncho3d/tri-zero), [B0](https://github.com/zruncho3d/boxzero), [X0](https://github.com/zruncho3d/double-dragon), [D0](https://github.com/zruncho3d/DuelingZero), [DX](https://github.com/zruncho3d/DuelingX), [ZeroPanels](https://github.com/zruncho3d/ZeroPanels), [ZeroClick](https://github.com/zruncho3d/zeroclick), [NoDropNuts](https://github.com/zruncho3d/f-zero/tree/main/STLs/NoDropNuts), [Poke](https://github.com/zruncho3d/poke), [Nudge](https://github.com/zruncho3d/nudge), and more.

 :heart: *-Zruncho*

## Updates and timeline

* 2025-02-15 Started the GitHub conversion process

TODO: add key timelines details

## Credits

TODO: note all beta-program members with contributions