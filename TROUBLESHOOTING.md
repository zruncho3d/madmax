## Troubleshooting Notes

### Failed docking and/or toolchanges
* Check for debris near the Maxwell coupling.
* Check for fully-seated magnets and that the FHCSes on the head are at the right length.
* Make sure the top Maxwell screw is fully seated; this once likes to vibrate loose.
* If steppers miss steps during a print, all bets are off.  Make sure all speeds are well within a margin of safety.  Autospeed by Anonoei is highly recommended to quantify your top-end speeds and accelerations; you can then derate for confidence.
* Check homing quality.  Sensorless homing is not as trustworthy, and the variation may seem random.

### Magnets escaping
* If magnets are escaping, your magnet-retention FHCSes are likely too small.
* Or, the plastic is deforming and enabling the magnets to pop out.  Check for plastic deformation.  In the worst case of a hot chamber, your print material (if ABS or ASA) may not have the needed temp tolerance.

### Maxwell-probing failures
If seeing "Probe triggered prior to movement" errors:
* Ensure that the front of the bed is not more than 1.5mm above the rear; that causes unexpected effects that look like probe issues, when the bed is hit during the XY travel.
* Make sure the electrical contacts on the plate and carriage do not need tightening.
* Make sure the toolhead-board crimp terminals are fully inserted and reliable.  Marginal crimps + twisting to add them to a toolhead can trigger a wire failure here.

### Maxwell-probing variability
Sometimes this can cause ZTA or QGL failures.
* If variability is too high, check for crud. A quick buff of the button heads with ScotchBrite can help. For the pins try a Q-Tip with isopropanol.
* Plate:
* Check that the 3 Maxwell screws on the plate are fully tight.  The upper screw, in particular, may loosen with time and vibration, and loctite is recommended.
* Check that the two lower screws connecting to the toolhead are fully tight; these are near heat, and like to loosen due to plastic creep.
* Check that the crimp connections to the toolhead board are solidly crimped; with insertion/removal cycles these sometimes fail, and tend to be the last thing to blame.
* Check that the two MiniSB hotend-mount screws are tightened fully.  These also like to loosen with time and heat.
* Carriage:
* Check that there is no play in the pins on the carriage, when pressed.
* Check that the two FHCSes are fully tightened.  These like to loosen with time and heat, due to proximity to the bed.

### Nudge failures
* "Probe triggered prior to movement"
  * Look at the probe.  Is it touching, where it is?
    * May need a bit more ‘spread’, or at least, a more accurate position for the given spread.
    * Not touching?
      * Probe triggered prior to movement - check resistance on Nudge; consider drift.
* Probe triggered partway through - add spread, to cover a different direction
  * Also, make sure the head is not hitting front-motion physical limits.
* Other?  
  * Check wiring qualit: ensure a reliable connection after many hits and in different places; could be from a failing umbilical or toolhead board cable.