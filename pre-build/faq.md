# Frequently Asked Questions

## Printing Parts

### Can I print in (PLA, PETG, resin, etc.)?

Voron printers are designed to be able to print ABS and other materials that can require elevated chamber temperatures in excess of 60C.  As a result materials that have a heat deflection temperature or glass transition temperature of 90C or higher are strongly recommended for making the Voron components from.  While other materials may meet the requirements, from a cost/benefit perspective, ABS and ABS+ are the most recommended materials.

Most hobby-grade resin prints have issues with long-term dimensional stability.  Many of them will continue to shrink as they slowly dry out, making them unsuitable for long-term structural use.  There are many commercial resins that would likely work but there is no definitive list at this time.

If the prospective Voron owner is not currently able to print in ABS for any reason, we recommend looking at the Voron print-it-forward (PIF) program.  Individuals can submit a request for another Voron owner to print the minimum functional parts for them.  There are costs and wait times associated.

### How much filament do I need?

Typical printers require approximately 1.5kg of the primary color and 0.3kg of the alternate color, assuming no failed or reprinted parts.  Most people end up reprinting a few parts and a few mods, so plan on 2kg of the primary color.

## Electronics

### Why an SKR 1.4?  What about Turbo?

The BTT SKR controller is inexpensive and extremely capable for the purpose.  Either an SKR 1.3 or 1.4 is recommended and can be used.  While both controllers have different pin configurations, they use the same controller chip.  BTT is no longer producing the 1.3 and it will eventually be unavailable.

The Turbo version is certainly usuable, but the additional speed is not required since most of the computing is offloaded by the Raspberry Pi.

### Can I use sensorless homing?

The CoreXY configuration does not support sensorless homing since both motors are active for both X and Y.  For V1 and V2, there is an external Z endstop switch that is designed to set the Z distance based on the nozzle height so sensorless homing is not required.

## Parts

### Dragon standard flow or high flow?

The Dragon standard flow is capable of supporting nozzles up to 0.6mm.  If planning on using 0.8mm nozzles or larger, the high flow is recommended.

### What are the hammer nuts used for?

The hammer nuts are intended to be used with the panel clips to allow easier removal and reinstallation.  It is possible to apply some locktite and create quarter-turn fasteners.

### What is the Kapton Tape used for?

The inductive probe in the toolhead is somewhat heat sensitive.  The kapton tape is helpful to be applied to the inductve probe to protect it from radiant hot end heat.

### What lube should I use?

The currently recommended lube for the linear rails is Mobilux EP2.  Either Super Lube or EP2 is recommended for the extruder gears.

## Assembly

### How square does the frame need to be?

Measured on the outer diagonals, the frame should be within 2mm.

### How is the deck panel attached?

The deck panel is sandwiched between the DIN rails and the bed rails.  The M5 bolts go into the DIN rails, through the deck panel, and into nuts in the bed rails.

### Should I clean the rails?

Most linear rails are packaged with a simple machine oil applied to the rails and carriages for transport.  It is recommended that the rails be cleaned with isopropyl alcohol (IPA) to remove the machine oil and the proper grease applied.  If the linear rails are packaged with the carriages installed, the carriages should not be removed for cleaning.

### What gauge wire should I use where?

The gantry wiring should be all 24 gauge wire except for the hot end heater, which should be wired with 20 gauge.  This will permit all of the wires to fit within the drag chains.  The power wiring (AC and DC) should be at least 20 gauge, preferably larger (18 or 16 gauge).

### PTFE or Silicone wire?

The BOM currently specifies silicone wire for bend and heat toleraance.  For an increased cost, PTFE wire is a option.  PTFE insulation is thinner and slicker, making it more effective in the drag chains.
