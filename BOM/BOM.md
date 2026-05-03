## BOM.md
Prelim BOM - boring, by design!  Reasonable, with the exception of the Acetal pins.

### Carriage Parts
 * Maxwell Pins
   * **2x metal pins**
     * Preferred: ⅛” dia x ½” length
       * Amazon: [uxcell 1/8-Inch x 1/2-Inch Dowel Pins](https://www.amazon.com/dp/B09M84DNT6)
       * McMaster: [Dowel Pins](https://www.mcmaster.com/products/dowel-pins/dowel-pins-2~/dowel-pins-1~~/length~1-2-2/length~3-8-1/length~7-16/diameter~1-8/diameter~0-125/material~steel-2/material~stainless-steel-2/material~6061-aluminum/material~grade-2-titanium/): [416 Stainless](https://www.mcmaster.com/98380A471/) OR [316 Stainless](https://www.mcmaster.com/97395A441)
     * ⅜" length is acceptable too
     * Yes, you can rough-cut bar stock, or even have them stick out a bit in both directions. It’s only the center part touching the BHCS that matters; ends can be a mess and nobody will see it.
     * If you find 3mm locally, that’s fine too.  You’ll have to export your own STLs in that case.  In that case, 12mm is preferred, but 10mm or 14mm will also work.
   * **4x plastic pins**
     * Best: POM (Polyoxymethylene) ⅛”: sold as Acetal, Delrin or Kocetal. POM-H and POM-C should work equally well in this application.
       * McMaster: [Pre-cut 1/8" x 1/2" pins](https://www.mcmaster.com/97155A426/) OR [1/8" stock](https://www.mcmaster.com/catalog/130/4126/8497K11) which cuts with large wire cutters.
     * Probably fine: steel pins, same as above, but will yield higher force.
     * Not OK: Teflon (PTFE) - deforms too quickly.
     * If you find 3mm locally, that’s fine too.  You’ll have to export your own STLs in that case.
     * These are English sizes because we couldn't source 3mm Acetal rods.
     * We have data (measured friction coefficients, probe forces with various materials), and some is at the bottom of [STORY.md](STORY.md).
 * Belt Pins
   * **2x 3mmx35mm steel pins**
     * Rounded ends are best (look for "locating dowel round head" or similar), but the usual chamfered pins work fine too
     * AliExpress: [3mm x 35 pins](https://www.aliexpress.us/item/3256803440853860.html)
     * Amazon: [uxcell 3mm x 35mm Dowel Pin](https://www.amazon.com/gp/product/B07M9TS54L)
     * McMaster: [3x34mm, sold individually](https://www.mcmaster.com/91595A117/) OR [3x36mm, pack of 25](https://www.mcmaster.com/91595A140/)
     * Alternately, use M3x30 SHCS/BCHS you have lying around.
     * Alternately, use M3x35 SHCS/BHCS with a nut or two on top.
     * Alternately, use ⅛“ pins; requires drill-out of plastic and will affect your choice of tubes. Example: McMaster [hardened steel pins, ⅛” x 1⅜“](https://www.mcmaster.com/98380A478/)
   * **2x M3 “Voron standard” heatsets**
     * Will fit onto pins after being drilled out.
     * Different spec M3 heatsets are fine
 * Belt Clips (a.k.a. SpeedClips)
   * **2x M3x10 BHCS**
   * **2x MakerBeam XL T-nuts** (from V0 parts list)
      * Amazon: [MBXL T-nuts](https://www.amazon.com/MakerBeam-XL-MakerBeamXL-15x15mm-Diameter/dp/B06XHQHD4H)
      * Can make your own, too, in a pinch.
   * **2x Metal Tubes**
     * These are metal tubes, into which the belt pins go.
     * Width: Two sizes are recommended:
       * Metric: 4mm OD, 3.2mm ID
       * English: 5/32" OD (3.97mm) x 0.014"
     * Length: varies by the width of your belts and the gap between the belt paths.
       * File to length.  A printed cuboid with matching sized hole for your tubing’s OD works great here to get a flat file and do that quickly, vs holding it with your fingers.  Reaming/using a drill bit on the cut tube will make it smooth
       * MGN9H: 14.5mm (slightly below 15mm is fine)
       * MGN12H with 6mm belts: 15.5mm for larger 4mm belt gap.
       * MGN12H with 9mm belts: 21.5mm
     * Material:
       * Stainless steel is best
         * Stainless will be stronger, but slightly harder to cut (esp. with a hacksaw) and file. Fortunately, the walls of this tubing are fairly thin, so it’s not so hard to work, even using hard stainless steel.
       * Aluminum is fine
       * Brass is OK
       * PTFE: only in a pinch, until the real parts arrive.
         * Yes, you can use drilled-out 4mm / 3mm PTFE tube, but it will deform under the forces and experience higher friction.
     * Sources:
       * Local hardware stores
         * Ace Hardware: K & S Precision Metal #8103 Round Aluminum Tube from Ace Hardware
       * McMaster:
         * [Welded Tube](https://www.mcmaster.com/50415K59/) (welded, not smooth bore, but confirmed to be OK)
         * [Welded Tube, 4mm OD, 3.5mm ID](https://www.mcmaster.com/50415K61) (acceptable also welded).
         * [316 Stainless](https://www.mcmaster.com/89785K816-89785K217/)
         * [304 Stainless](https://www.mcmaster.com/89895K716-89895K217/)
 * Main electrical connections
   * **2x M3x8 stainless FHCS**: can be 10mm too, but MUST BE CONDUCTIVE.  No black alloy here.
   * **2x M3 shims**: 0.5 thick, 7mm OD
   * **2x M3 nut**
 * Other
   * **4x M3x8 SHCS**: for carriage attachment (BHCS OK as workaround)
 * Homing (**read carefully - depends on type**)
   * Sensored (endstop-based) homing (recommended)
     * **~120mm wire 22-26 gauge**; must be less than 1.8mm OD
       * [AliExpress wire](https://www.aliexpress.us/item/2251832766791205.html)
     * **1x Omron D2F**: or similar.  Usual “Voron standard” switch for X-endstop (plus endstop of choice for Y)
     * **2x M2 self-tapping screws**
   * Sensorless homing (not recommended)
     * **60mm wire 22-26 gauge**; must be less than 1.8mm OD
       * [AliExpress wire](https://www.aliexpress.us/item/2251832766791205.html)
 * Magnets
   * **6x 6x3mm N52 (Neodymium) magnets**: actual amount to use will depend on toolhead weight and bed stability (4-6x)
     * **THESE MUST BE REAL N52. Do not try Amazon or AliExpress.  Use known-good vendors.**
     * Example: [Fabreeko N52](https://www.fabreeko.com/products/n52-neodym-magnet-6x3mm-schwarz)
 * Optional Magnet-Retaining Screws (required if used in chamber; probably optional if in free air)
   * **3x M3x8 FHCS**; can be 10mm depth.
     * MUST BE 5.8-5.9mm head dia, not 5.5mm head dia.
     * Black alloy steel or shiny stainless are both OK here; they’re not forming an electrical connection.
   * **3x M3 nuts**

### Plate Parts (xN): per head
NOTE: **per head totals**, below:

 * Maxwell Coupling
   * **2x M3x8 BHCS** - must be conductive (stainless), not coated alloy
   * **1x M3xX** for top screw (depends on head choice)
     * Does not need to be conductive.  MUST have no writing!  MUST not have a rough surface!  Needs to be shiny and smooth.
   * **5x M3 nut** (3 should be in 2.2-2.4mm thickness; find 3 that match)
 * **2x M3x8 BHCS** (lower toolhead attachment)
 * **6x 6x3mm N52 magnets** (see note for carriage)
 * **4x M3 “Voron standard” heatsets**
 * **2x M3 Jam Nuts** (1.8mm thick) OR 8x M3 6mm-OD shims (0.5mm thick)
 * **2x ring crimp terminals with 3mm hole**
 * **250mm 2-position zip wire** for connection to toolhead board; see note on sizing, in carriage section
 * Optional Magnet-Retaining Screws
   * **3x M3x6 FHCS**; alloy or steel OK
   * **3x M3 nut**

### Dock- and toolhead-dependent parts
Below are starter requirements.  Make sure to check with your dock/toolhead vendor first.

* Docks (x2): **per dock** below; depends on specific dock and printer, but commonly:
  * **3-4x 6x3mm N52 magnets**
  * **M3 or M5 mounting screws**
  * For Xol/A4T dock by `andrewmcgr`:
    * Each dock:
       * 8x M3x8 SHCS or BHCS
       * 8x Voron M3 headsets
       * 2x M5x10
       * 2x M5x20
       * 4x M5 extrusion nuts, 3x 6x3mm magnets
* Second Toolhead - check with toolhead vendor first:
  * All the same stuff a typical hotend will have (fans, hotend, toolhead board, bowden, screws, ECAS, …)
  * DragonBrick/RapidBrick - per head
    * 3x M3x8 FHCS - must be alloy!
  * XOL/A4T by `andrewmcgr`:
    * Each toolhead: 3x M3x8 or M3x6 FHCS (must be strongly magnetic, i.e. steel and not stainless), 1x M3x16, 1x M3x12 SH or BH, 2x extra heatsets
  * AntHead
    * See AntHead repo
    * OmniBrick - per head
      * 4x M3x8 FHCS - must be alloy!
      * 2x heatsets (add in post; a bottom rear of cowl)
      * 1x M3x6 FHCS (for Huvud shroud)
* Nudge (optional)
  * Not technically required, but highly recommended.  See its GitHub page: [https://github.com/zruncho3d/nudge](https://github.com/zruncho3d/nudge)
* Additional Spool Holder
* Additional Bowden/ECAS
* Upgraded PSU
  * An upgraded PSU might be necessary. Either go for a comfortable margin or buy an inline power meter (like a Watt’s Up) and measure consumption if you’re not sure.
