## MadMax - the crazy-simple toolchanger *conversion* for your CoreXY printer

Enable multi-material printing *on the printer you already own* - with low cost, low effort, low filament waste, and fast multi-material switching.

![](Renders/Front_and_back_no_trans.png)

| ![gif](*.gif) | ![gif](*.gif) | ![gif](*.gif) |
| --- | --- | --- |
| Toolchanging | Printing | Probing (with Nudge) |

TODO: table with GIFs covering the main steps - ideally all perfect loops, all vertical

**MadMax is currently in active beta**, with over 10 builds doing reliable two-head prints:  

TODO: finish Beta member table with standard front views, parts examples, and descriptions

| Printer | Image | Sample | Description |
| --- | ---- | ---- | ---- |
| Zruncho's T0 120 (MM.000) | ![](Images/Builds/zruncho_0_front_1920.jpg) |  ![](Images/Builds/zruncho_0_part_1080.jpg) | Tri-Zero+BoxZero, Vampire Bat, V0/T0 docks, Nudge, custom rear-shift bed parts, 2x OmniBrick heads, 2x PapLite belt extruders, 2x custom brush/blockers. <br><br>The original!|
| Rob's V0 120 (MM.001) |  | |
| andrewcgr's VT 350 (MM.002) |  | |
| Ambrosia's Metal VT (MM.003) |  | |
| Telxoid's Tridex 250 (350 wide) (MM.004) |  | |
| Max's HX9 120 (MM.005) |  | |
| Rob's VT (MM.006) |  | |
| Caza's Metal Micron (MM.007) |  | |
| Yeri's SF 160 (MM.008) |  | |
| Sam's V0.2 120mm +30X (MM.009) |  | |
| r2pdx's Micron 180 (MM.010) | ![](Images/Builds/r2pdx_10_front_1920.jpg) | ![](Images/Builds/r2pdx_10_part_1080.jpg) | Micron 180r1, 2x Anthead toolheads with modified ducts and WWG2 extruders, Nudge, gantry-mounted docks by r2pdx (also tested frame mounted docks).<br><br>On its way to becoming doomed! |

Learn more from videos:
* [Canuck Creator interviews Ambrosia](https://www.youtube.com/watch?v=dB9FqNF6or0&t=164s) - with a MadMax Trident
* [Speedclips.... they're real, and they're spectacular](https://www.youtube.com/watch?v=UsWV_GbRdjc)
* Fast toolchanges and motion with Andrew's build
* Core Build
* Selecting a Toolhead

TODO: add videos for intial learning

**This is an advanced mod**: you must be comfortable with modifying Klipper configs and debugging related error messages.

**This project is in beta**: parts are well-tested/well-trusted and docs are nearly complete, but expect changes to parts and expect minor gaps in docs.  

Earlier in a project is where your efforts will have the highest impact, so now's the time to jump onboard!

## New part concepts, all easily sourced

| ![](Renders/Core_Front_Iso.png) | ![](Renders/Carriage_MGN9H_Front_Iso.png) | ![](Renders/Plate_MGN9H_Front_Iso.png) | ![](Renders/Clips_Front_Iso.png) | ![](Renders/T0_Dock_Front_Iso.png) |
| --- | --- | --- | --- | --- |
| ![](Renders/Core_Rear_Iso.png) | ![](Renders/Carriage_MGN9H_Rear_Iso.png) | ![](Renders/Plate_MGN9H_Rear_Iso.png) | ![](Renders/Clips_Rear_Iso.png) | ![](Renders/T0_Dock_Rear_Iso.png) |
| Core<br>(Carriage + Plate + Clips) | Carriage | Plate | Clips | Sample Dock (V0/T0) |

A combination of new parts makes it possible:
* **Core:** A new “pins and screws” magnetic [Maxwell](https://en.wikipedia.org/wiki/Kinematic_coupling) coupling enables head attach/detach, head detection, AND probing.  
  * Yes, you heard that correctly!   The core carriage+plate mechanism _is_ the probe, if you want.  The Maxwell coupling is engineered to slide in place with low friction, enabling high-quality probing up there with Tap and Boop, but lighter, lower-cost, and with more stable motion.  Here's a sample probe run:
  `probe accuracy results: ... range 0.002031,... standard deviation 0.000548`.  Not bad!  In fact, you can use the core on non-toolchangers too, as a Tap/Boop replacement.
* **Clips:** The new SpeedClips belt clips are the fastest belt attachment mechanism in the west, plus enable repeatable tensioning.
* **Docks:** The docks use simple keyslots and magnets, with the toolhead modified to add ferrous flat-head screws.  It's all light, low-cost, small, and simple.

All parts use easily-available purchased components, like pins, screws, and magnets.  You may already have everything you need to build this in your toolbox!   It’s more straightforward mod than you might think.

So, what's the catch?
* Some lost XY build area, when printing with two heads. Space loss is inherent to all toolchangers, but for single-head prints, you can detach the second head in seconds, to restore nearly 100% of the original build volume.
* No positive lock on the toolhead - only a magnetic hold.  In practice, this works fine, and means that no complex locking mechanism or motors are needed, plus enables the probing method.  It's safe; should the head detach for any reason, the firmware immediately safes the printer, just like with any other fault.
* Some printers and toolheads will need a completed port.
* No builds beyond two heads, yet - but this is the sweet spot for high-speed multimaterial.

That’s about it.  Read on to learn what a MadMax can do.

## Enable serious new capabilities

This mod is for those who want a more capable printer.

The surprise is that you can enable *many* new capabilities, with only about $100, one night of printing, one night of building, and one night of configuration and tuning.

| Use case | Multiple colors  | Multiple materials | Full-contact supports | Tap/Boop replacement |
| --- | --- | --- | --- | --- |
| Example(s) | ![](Images/r2pdx_dragon.jpg) |  ![](Images/Rob_flexbox.png) | ![](Images/Ambrosia_magpie_small.jpg)  | ![](Images/Core_on_scale.jpg) |
| Notes | Dragon printed by r2pdx, on MM.010 | Flexible box printed by Rob on MM.001 | Magpie printed by Ambrosia on MM.003  | Core weighs ~50g  |
| Benefits |  No adhesion issues/bleed vs MMU, vastly reduced waste and delay, can use TPU | No adhesion/mixing issues vs MMU, vastly reduced waste and delay | Clean support interfaces, with no mixing issues vs MMU | Lighter weight and better IS results, plus detach head for easy maintenance |

Unlike toolchanger designs that require up/down docking motion, MadMax supports static-gantry printers (like Voron Trident), *without* the added cost/complexity of a [liftbar](https://github.com/viesturz/tapchanger/blob/main/Dock/Liftbar/Liftbar.md).  

XY-only toolchanges are lightning-fast, which can speed up overall print time, improve print quality, simplify print tuning, and reduce priming waste.

## An entire toolchanger ecosystem

MadMax is more than just the core and dock interfaces; already, **it is an entire toolchanger ecosystem** covering many common [Voron](https://vorondesign.com/) and [Printers for Ants](https://3dprintersforants.com/) printers, plus many open-source toolheads and extruders.  

| Carriages | Belt Configs | Toolheads (core only) | Toolheads (to docks) | Printers |
| --- | --- | --- | --- | --- |
| 2 | 3 | 4+ | 7+ | Lots |
| MGN9H<br>MGN12H | 6mm w/3mm sep<br>6mm w/3mm sep<br>9mm w/4mm sep| MiniSB<br>OmniBurner<br>DragonBurner<br>RapidBurner<br>A4T<br>XOL | DragonBrick<br>RapidBrick<br>AntHead<br>A4T<br>A4TBrick<br>OmniBrick<br>XOL<br> |  Voron Trident<br>Voron Zero<br>Micron<br>Salad Fork<br>Tri-Zero<br>Pandora's Box<br>

If you don’t see your printer in the list below, adding it tends to be straightforward.

The main requirement is a front-facing MGN9H or MGN12H linear rail and XY head motion, so bed slingers and rail riders are out.

A few of the supported heads: A4T, AntHead, OmniBrick, DragonBrick:

| ![](Images/Toolheads_Rear.jpg) | ![](Images/Toolheads_Front.jpg) |
| --- | --- |

Note that MGN9H plates have a diamond of magnets, whereas MGN12H plates have a square of magnets.

## Easy to print, build, and configure

All parts are easy and fast to print, with no large overhangs, no large bridges, and supports included.  

Here's a full plate for the MadMax core parts for a conversion:

![](Renders/plate.png)

To this plate, you would add printer-specific toolheads and docks.

The entire conversion can be done in an evening, as covered by instructional videos, and no individual steps are hard.

TODO: Video: building MadMax: core build

TODO: Video: building MadMax: plate build

TODO: Video: building MadMax: toolhead choices

TODO: Video: building MadMax: dock samples

Sample Klipper configuration is available in this repo, for [Viesturz' klipper-toolchanger](https://github.com/viesturz/klipper-toolchanger), but [TypQxQ's KTC2](https://github.com/TypQxQ/KTC) and [Bikin Toolchanger](https://github.com/Bikin-Creative/Lineux-Toolchanger/tree/main/Klipper) are also potential choices.

TODO: Video: Configuring MadMax with klipper-toolchanger (show Klipper config)

Calibration is fully automated (using [Nudge](https://github.com/zruncho3d/nudge)), can run on every print (using [r2pdx's macros](https://github.com/joseph-greiner/klipper_tc_automatic_offset_calibration)), and includes head crash detection for safety.

TODO: Video: Initial MadMax calibration (XY positions, reliability)

TODO: Video: head crash detection for safety!

Every-print auto-calibration looks like this:

TODO: Video: Auto-calibration between nozzles

Automatic offset calibration is a big deal for the overall experience of a toolchanger, because it removes the main source of pain relative to automated filament changers.  You can change hotends or adjust the mount - things which can affect offset calibration - and there’s no work to do, because calibration is automatic.  Plus, any differences in offsets due to temperature or changes to the positions of the heads or the frame are automatically accounted for, by probing at the operating temp.

### Key features
* Support for a wide range of printers and toolheads, including static-gantry printers
* Fast toolhead changing for faster, better multi-extruder prints
* Bonus Maxwell-coupling-driven nozzle probing (!)
* Toolhead failure detection without extra parts
* Bonus pragmatic features:
 * Pinned carriage enables reproducible retensioning
 * Fully reversible conversion process
 * Documented and simplified steps for toolchanger setup with Klipper
 * Reliable: no glue, no servos to fail, no liftbar parts to fail

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

This one took a lot of prototypes and time.  Here's a partial set:

![](Images/Progression_core.png)

## Updates and timeline

* 2025-02-15 Started the GitHub conversion process
* 2024-11-04 Beta-3 files shared: new CAD, stiffer, better airflow, washers for wires, lots more
* 2024-09-12 Beta-2 files shared: MGN12 support, adds 120 degree option, better probe wiring, locking screws for magnets, nuts/screws instead of set screws ... lots of changes
* 2024-08-XX Spinoff: automatic magnet tester built - tests magnet strength, probe force, and more
* 2024-06-08 Proper closed beta program launches, with beta-1 files
* 2024-05-14 First two-extruder prints
* 2024-04-01 Spinoff: [Vampire bat](https://github.com/zruncho3d/vampire_bat) release
* 2024-04-10 Spinoff: [Nudge](https://github.com/zruncho3d/nudge) release
* 2024-01-14 Spinoff: manual magnet tester
* 2023-12-10 Started collaborating on MadMax, as a front-mount TC
* 2023-09-02 First desk toys with Maxwell couplings, intended for a TC

## Credits

Thanks to all those who contributed to the beta program in some form, especially `caza` for a range of early testing, plus those who got all the way and contributed designs - `Rob`, `andrewmcgr`, `Ambrosia`, `Telxoid`, `Max`, `Sam`, `r2pdx`, and more - plus those whose feedback provided encouraging - `Ankurv`, `hartk`, `clee`, `chirpy`.
