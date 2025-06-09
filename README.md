## MadMax - the crazy-simple toolchanger *conversion* for your CoreXY printer

Enable multi-material printing *on the printer you already own* - with low cost, low effort, low filament waste, and fast multi-material switching.
<br><br>

 | ![](Renders/Front_and_back_no_trans_small.png) | ![gif](Videos/Yell_Toolchange.gif) | ![gif](Videos/Andrewmcgr_printing_short.gif) |
| --- | --- | --- |
| Solid Core<br>new plate + carriage design using Maxwell coupling | Fast Toolchanging<br>(`Yell`'s E3-to-Trident with AntHeads)  | Quality Printing<br> (`Andrewmcgr`'s VT 350 with A4Ts) |

<br><br>
**MadMax is currently in active beta**, with over 12+ completed builds doing two-head printing:
<br><br>

| Printer | Image | Sample | Description |
| --- | ---- | ---- | ---- |
| Zruncho's T0 120 (MM.000)| ![](Images/Builds/zruncho_0_front_1920.jpg) |  ![](Images/Builds/zruncho_0_part_scaled.jpg) | T0+B0, Vampire Bat, Nudge, custom rear-shift bed parts, OmniBrick heads, PapLite belt extruders, docks + brushes/blockers by Zruncho.|
| Rob's V0 120 (MM.001) | ![](Images/Builds/rob_1_front_1920.jpg) | ![](Images/Builds/rob_1_part_1920.png) | Voron Zero, Vampire Bat, DragonBricks, V0 docks by Rob, Custom K1 extruders by Rob.|
| andrewmcgr's VT 350 (MM.002) | ![](Images/Builds/andrew_2_front_1920.jpg) | ![](Images/Builds/andrew_2_part_scaled.png) | Trident 350, A4Ts, Sherpa Minis, TMC 4671 closed-loop servo XY drives, BFI, Cartographer. Docks, brushes, carriage, plate by Andrew.|
| Ambrosia's Metal VT (MM.003) | ![](Images/Builds/ambrosia_3_front_1920.jpg) | ![](Images/Builds/ambrosia_3_part_scaled.png) | Metal Trident with DragonBricks, Trident stalagmite docks by Ambrosia, as seen on [Canuck Creator](https://www.youtube.com/watch?v=dB9FqNF6or0&t=164s)! |
| Telxoid's Tridex 250 (350 wide) (MM.004) | ![](Images/Builds/telxoid_4_front_1920.jpg)  | ![](Images/Builds/telxoid_4_part_scaled.png) | Tridex, A4TBrick, PapLite belt extruders, docks + brushes/blockers by Telxoid.  Running y-assist CoreXY!
| Max's HX0 120 (MM.005) | ![](Images/Builds/runningsystemchanger_5_front_1920.jpeg) | ![](Images/Builds/runningsystemchanger_5_part1_scaled.png) | HX0+B0, VB, DBs, custom PapLite Slim mount, side-mount TH board, Y-shift HammerHead bed by Max.|
| Rob's VT (MM.006) | ![](Images/Builds/rob_6_front_1920.jpg) | ![](Images/Builds/rob_6_part2_1920.jpg) | RapidBrick heads by Rob, Trident stalagmite docks by Ambrosia.|
| Caza's Metal Micron (MM.007) | ![](Images/Builds/caza_7_front_1920.jpg) |  ![](Images/Builds/caza_7_part_scaled.png) |  Yavoth heads by Caza, Orbiter extruders, Micron Docks by Caza.
| Yeri's SF 160 (MM.008) | ![](Images/Builds/yeri_8_front_1920.jpg) | ![](Images/Builds/yeri_8_part_scaled.png) | Salad Fork wraparound docks by Yeri, DragonBrick heads by Rob, G2Z extruders.|
| Sam's V0.2 120mm +30X (MM.009) | ![](Images/Builds/sam_9_front_1920.jpg) | ![](Images/Builds/sam_9_part_1920.jpg) | Docks by Rob, DragonBrick heads by Rob, LGX Lite extruders, customized extra-wide Vampire Bat gantry by Sam.|
| r2pdx's Micron 180 (MM.010) | ![](Images/Builds/r2pdx_10_front_1920.png) | ![](Images/Builds/r2pdx_10_part_scaled.png) | Micron 180r1, AntHeads with modified ducts and WWG2 extruders, Nudge, gantry-mounted docks by r2pdx (also tested frame mounted docks).|
| Yell's [Ender3-to-Trident-conversion](https://github.com/yell3D/Ender3dent) (MM.011) | ![](Images/Builds/yell_11_front_1920.jpg) |![](Images/Builds/yell_11_part_1920.jpg) | E3dent, AntHeads, GBB15 gantry board/CAN bridge; docks, bucket & brush by Yell. Crossbar for >= 2 heads!|
| Vlad's 300-ish Trident (MM.012) | ![](Images/Builds/vlad_12_front_1920.jpg) |![](Images/Builds/vlad_12_part.jpg) | A4T, Sherpa Mini, Andrew's add-on brackets, extended Ambrosia's docks. Eddy current XY toolhead alignment! |

Learn more from videos:
* [Canuck Creator interviews Ambrosia](https://www.youtube.com/watch?v=dB9FqNF6or0&t=164s) - with a MadMax Trident
* [Speedclips.... they're real, and they're spectacular](https://www.youtube.com/watch?v=UsWV_GbRdjc)
* Core Build (coming later)
* Selecting a Toolhead (coming later)

**This is an advanced mod**: you must be comfortable with modifying Klipper configs and debugging related error messages, and potentially, doing small CAD mods to fit your printer.

**This project is in beta**: parts are well-tested/well-trusted and docs are complete, but parts may change in the future.

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

All parts use reasonably-sourceable components, like pins, screws, and magnets. It’s a more straightforward mod than you might think.

So, what's the catch?
* Some lost XY build area, when printing with two heads. **Space loss is inherent to all toolchangers**, but for single-head prints, you can detach the second head in seconds, to restore nearly the full original build volume.
* No positive lock on the toolhead - only a magnetic hold.  In practice, this works fine, and means that no complex locking mechanism or motors are needed, plus it enables the probing method.  It's safe; should the head detach for any reason, the firmware immediately safes the printer, just like with any other fault.
* Some printers and toolheads will need some CAD work before they're print-and-play.
* The lower two BHCS screws on the coupling may wear with time and need replacement for reliable probing.  
* No builds seen beyond two heads, yet.

That’s about it.  Read on to learn what a MadMax can do.

## Enable serious new capabilities

This mod is for those who want a more capable printer.  The surprise is that you can enable *many* new capabilities, with only about $100, one night of printing, one night of building, and one night of configuration and tuning.

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
| 2 | 3 | 6+ | 7+ | Lots |
| MGN9H<br>MGN12H | 6mm w/3mm sep<br>6mm w/4mm sep<br>9mm w/4mm sep| MiniSB<br>OmniBurner<br>DragonBurner<br>RapidBurner<br>A4T<br>XOL | DragonBrick<br>RapidBrick<br>AntHead<br>A4T<br>A4TBrick<br>OmniBrick<br>XOL<br> |  Voron Trident<br>Voron Zero<br>Micron<br>Salad Fork<br>Tri-Zero<br>Pandora's Box<br>[E3-to-Trident-conversion](https://github.com/yell3D/Ender3dent) |

If you don’t see your printer in the list below, adding it tends to be straightforward.

The main requirement is a front-facing MGN9H or MGN12H linear rail and XY head motion, so bed slingers and rod riders are out.

A subset of the supported heads: A4T, AntHead, OmniBrick, DragonBrick:

| ![](Images/Toolheads_Rear.jpg) | ![](Images/Toolheads_Front.jpg) |
| --- | --- |

Note that MGN9H plates have a diamond of magnets, whereas MGN12H plates have a square of magnets.

## Easy to print, build, and configure

All parts are easy and fast to print, with no large overhangs, no large bridges, and supports included.

Here's a full plate for the MadMax core parts for a conversion:

![](Renders/Plate.png)

To this plate, you would add printer-specific toolheads and docks.

The entire conversion can be done in an evening, as covered by instructional videos, and no individual steps are hard.

Sample Klipper configuration is available in this repo, for [Viesturz' klipper-toolchanger](https://github.com/viesturz/klipper-toolchanger), but [TypQxQ's KTC2](https://github.com/TypQxQ/KTC) and [Bikin Toolchanger](https://github.com/Bikin-Creative/Lineux-Toolchanger/tree/main/Klipper) are also potential choices.

Calibration is fully automated (using [Nudge](https://github.com/zruncho3d/nudge)), can run on every print (using [r2pdx's macros](https://github.com/joseph-greiner/klipper_tc_automatic_offset_calibration)), and includes head crash detection for safety.

Automatic offset calibration is a big deal for the overall experience of a toolchanger, because it removes the main source of pain relative to automated filament changers.  You can change hotends or adjust the mount - things which can affect offset calibration - and there’s no work to do, because calibration is automatic.  Plus, any differences in offsets due to temperature or changes to the positions of the heads or the frame are automatically accounted for, by probing at the operating temp.

### Key features
* Support for a wide range of printers and toolheads, including static-gantry printers
* Fast toolhead changing for faster, better multi-extruder prints
* Bonus Maxwell-coupling-driven nozzle probing
* Toolhead failure detection without extra parts
* Bonus pragmatic features:
 * Pinned carriage enables reproducible retensioning
 * Fully reversible conversion process
 * Documented and simplified steps for toolchanger setup with Klipper
 * Reliable: no glue, no servos to fail, no liftbar parts to fail

## What's here?
- #### [Getting Started](GETTING_STARTED.md) - select a printer, toolhead, and extruder, amongst choices
- #### [BOM](BOM.md) - parts to procure
- #### [Instructions](INSTRUCTIONS.md) - print and build steps
- #### [Configuration](CONFIGURATION.md) - Klipper config and calibration
- #### [Story](STORY.md) - how and why this project came to be
- #### [Design](DESIGN.md) - notes on design choices; especially useful for doing ports
- #### [FAQ](FAQ.md) - covers questions you may have; worth a skim
- #### [Troubleshooting](TROUBLESHOOTING.md) - steps to diagnose the most-common errors

## Get Support

We now have a channel, `#madmax-toolchanger`, on the DoomCube Discord, in the misc-3dp area.  For now, this is the official home for all discussions and dev updates.  Go there!

[DoomCube Discord](discord.gg/doomcube)

## Support the creator
Like what you see?  [Buy me a coffee](https://ko-fi.com/zruncho3d) to show the love and enable future mods and content - stuff like [F0](https://github.com/zruncho3d/f-zero), [T0](https://github.com/zruncho3d/tri-zero), [B0](https://github.com/zruncho3d/boxzero), [X0](https://github.com/zruncho3d/double-dragon), [D0](https://github.com/zruncho3d/DuelingZero), [DX](https://github.com/zruncho3d/DuelingX), [ZeroPanels](https://github.com/zruncho3d/ZeroPanels), [ZeroClick](https://github.com/zruncho3d/zeroclick), [NoDropNuts](https://github.com/zruncho3d/f-zero/tree/main/STLs/NoDropNuts), [Poke](https://github.com/zruncho3d/poke), [Nudge](https://github.com/zruncho3d/nudge), [Vampire Bat](https://github.com/zruncho3d/vampire_bat), and more.

 :heart: *-Zruncho*

This one took a lot of prototypes and time.  Here's a partial set, which shows evolution from toys at the top, to little mods to try out the idea (green/gray near top left), to a range of increasingly reliable and solid carrriages and plates.

![](Images/Progression_core.png)

## Updates and timeline

* 2025-02-15 Started the GitHub conversion process
* 2024-11-04 Beta-3 files shared: new CAD, stiffer, better airflow, washers for wires, lots more
* 2024-09-12 Beta-2 files shared: MGN12 support, adds 120 degree option, better probe wiring, locking screws for magnets, nuts/screws instead of set screws ... lots of changes
* 2024-08-01 Spinoff: automatic magnet tester built - tests magnet strength, probe force, and more
* 2024-06-08 Proper closed beta program launches, with beta-1 files
* 2024-05-14 First two-extruder prints
* 2024-04-01 Spinoff: [Vampire Bat](https://github.com/zruncho3d/vampire_bat) release
* 2024-04-10 Spinoff: [Nudge](https://github.com/zruncho3d/nudge) release
* 2024-01-14 Spinoff: manual magnet tester
* 2023-12-10 Started collaborating on MadMax, as a front-mount TC
* 2023-09-02 First desk toys with Maxwell couplings, intended for a TC

## Credits

Thanks to all those who contributed to the beta program in some form, especially `caza` for a range of early testing, plus those who got all the way and contributed designs - `Rob`, `andrewmcgr`, `Ambrosia`, `Telxoid`, `Max`,  `Yeri`, `Sam`, `r2pdx`, 'Yell', 'Vlad', and more - plus those whose feedback provided encouragement - `Ankurv`, `hartk`, `clee`, `chirpy`, and more.
