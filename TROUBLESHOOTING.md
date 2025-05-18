## Troubleshooting Notes

**NOTE: The top issue is fake N52 magnets.** Both the docks and the core require proper, full-strength N52 magnets. If you have not sourced from a known-good magnet seller, this is the most likely issue.  Random AliExpress stores may sell N35s as N52s.

### Failed docking and/or toolchanges

* Check for debris near the Maxwell coupling.
* Check for fully-seated magnets.
* Check that the FHCSes on the toolhead (which fit into the slots) are tuned to  the right length for the docks; they should just about touch the magnets, to maximize grip.
* If steppers miss steps during a print, all bets are off.  Make sure all speeds are well within a margin of safety.  [Autospeed by Anonoei](https://github.com/Anonoei/klipper_auto_speed/) is highly recommended to quantify your top-end speeds and accelerations; you can then derate to add confidence.
* Check homing quality.  Sensorless homing is not as trustworthy as sensored (endstop-based homing), and the variation may seem random.  While the core and docks are designed to support misalignment beyond 0.5mm in all directions, they can only tolerate so much.

### Magnets escaping
If magnets ever escape, for any reason:
* Ensure your magnet-retention FHCSes are large enough.  These should be at least 5.8mm diameter; 5.5mm diameter screw heads won't do anything.
* Or, the plastic is deforming and enabling the magnets to pop out.  Check for plastic deformation.  In the worst case of a hot chamber, your print material (if ABS or ASA) may not have the needed temp tolerance.

### Maxwell-probing failures
If seeing "Probe triggered prior to movement" errors:
* Ensure that the front of the bed is not more than 1.5mm above the rear; bed misalignment can causes unexpected effects that look like probe issues, when the bed is hit during the XY travel.
* Make sure the electrical contacts on the plate and carriage do not need tightening.
* Make sure the toolhead-board crimp terminals are fully inserted and reliable.  Marginal crimps + twisting to add them to a toolhead can trigger a wire failure here.
* Ensure that there is visible daylight between the core and plate; if a rub develops, it can prevent the electrical contact from closing.
* Make sure the magnets are proper N52, as noted above.

### Maxwell-probing variability

The toasty environment near the toolhead can cause issues which yield a reduction in probing quality, especially ZTA or QGL failures, especially with a sub-0.01 tolerance.  However, the cause can also be elsewhere, in a way that can *appear* like a core issue.

**When diagnosing probe variability issues, run through all the possibilities here.**  We've never had a case where it wasn't one of the items listed below.

* Carriage:
  * Ensure that there is no crud near the pins, and preemptively clean them... ABS seems to leave a film over time.  A quick buff of the button heads with ScotchBrite can help. For the pins, try a Q-Tip with alcohol cleaner, followed by a reapplication of grease, followed by a bunch of probe cycles to settle the grease.
  * Ensure that there is no play in the pins on the carriage.
  * Ensure that no cracks are present on the carriage, especially near magnets, pins, and screws.  Look in all directions.
  * Ensure that all magnets are still there (!).
  * Ensure that the SHCSes which attach to the carriage are fully tightened, and that they're not too long.
  * Ensure that there is visible daylight between the core and plate; if a rub develops, the rub can lead to variable quality.  You may see jumps in probing of 0.1mm or so, if the friction to return is too high.  
    * Check for deformed plastic near the magnets and magnet-retention screws.
    * Check for daylight near the top screw; if this screw gets progressively tightened over time, the gap can close near that screw, and create a hard-to-see rub.  This issue has only appeared on MiniSB toolhead derivatives (which use a thin plate), and not on DragonBurner derivatives (which have a much thicker plate to spread out the force of the top screw).
  * Ensure that the electrical-connection FHCSes and wire connection are tight. Measure the resistance of the electrical connection to ensure that it's not the issue.
* Plate:
  * Check that any toolhead-attachment (non-Maxwell) screws are fully tightened. These like to loosen with time and heat, due to proximity to the bed.
  * For MiniSB-derived heads, Check that the two MiniSB hotend-mount screws are tightened fully. These also like to loosen with time and heat.
  * Check that the 3 Maxwell screws are fully tight. The upper screw, in particular, likes to loosen with time, so threadlocker is highly recommended.
  * Check that the crimp connections to the toolhead board are solidly crimped, by pulling on them.
  * Check for any physical damage to the lower two Maxwell-coupling screws.  These appear to wear over time, because the software steel heads rub on the hardened steel pins, and as they flatten, the ability of the toolhead to center reduces.  In addition, force when the coupling is reattached may dent them slightly.
  * Check that the non-electrically-connected pins (the other 4) are not dented.  PTFE will deform with time, temp, and pressure.  That's why Acetal is the spec'ed material, as it is a harder-wearing, yet still low-friction material.  If these pins are dented, it will be harder to get reliable probing.
* Z motion:
  * Ensure that Z pulley setscrews are tight and secured with threadlocker.  The higher probe force of the MadMax coupling (up to ~1kg) has a habit of revealing issues in the Z motion side.  A way to get evidence for such an issue is to run `PROBE_ACCURACY` near each Z attachment.
  * Ensure that each Z belt is at appropriate tension.  If a belt slips and one side is weaker, this can yield a peristent probe offset or reduced repeatability.
* Other:
  * Electrical connections outside the core can become loose too, like a failed umbilical wire or bad crimp on the mainboard or toolhead board side.

**If all of these methods still lead to subpar probing (0.02mm StdDev or higher), then replace the two lower BHCSes.**  These are the closest thing to a consumable.  In a few cases, we've scratched our heads, and replacing the BHCSes immediately returns the probe to perfect (sub-0.001 Std Dev) results.  The good news: two screws are cheap.


### Nudge probing failures
* "Probe triggered prior to movement"
  * Look at the probe.  Is it touching, where it is?
    * It may need a bit more ‘spread’, or at least, a more accurate position for the given spread.  Sensorless homing variability can trigger this occasionally.
    * Not touching?
      * Probe triggered prior to movement - check resistance on Nudge; consider drift.
* Probe triggered partway through - add spread, to cover a different direction.
  * Also, make sure the head is not hitting front-motion physical limits, or losing steps from any motion.
* Other?  
  * Check wiring quality: ensure a reliable connection after many hits and in different places; could be from a failing umbilical or toolhead board cable.