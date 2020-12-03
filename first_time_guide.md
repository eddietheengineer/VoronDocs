# Welcome

Welcome to the world of Voron printers!

This is a guide to help orient newcomers in selecting and building their first Voron printer.

# Printer Models

There are currently 4 printers in the Voron lineup.  One is not necessarily better than the other, just different.  All printers are capable of being fully enclosed to print ABS but can just as easily print PLA, PETG, or even Nylon.  All printers in the Voron lineup are designed to use a Raspberry Pi linked to one or more motor controller board(s) to manage all of the printer functions and interface controls.

## Voron 0

The [Voron V0](http://vorondesign.com/voron0) is a traditional coreXY design with the bed moving along the Z axis. It is a tiny 120mm^3 print area built with 1515 extrusions. It encloses naturally so printing ABS is possible. Currently, all single mechanical parts for V1 and V2 can be printed on a V0 bed. The design accounts for stock Makerbeam XL extrusion lengths (which come tapped) and standard MGN7 linear rail lengths, so scaling the design will start to increase cost or labor involved with tapping. The bed is also cantilevered which will also restrict scaling. This printer can be built for around \$400 USD. 

## Voron 1

The [Voron V1](http://vorondesign.com/voron1.8) is a traditional coreXY design where the bed moves along the Z axis. It is simpler to build compared to V2 and can be built for around \$1,000 USD. It encloses naturally so ABS or other temperature sensitive filaments can be printed easily. It uses rails for the X and Y axis so you can scale to a 300x300 plate. Z height is somewhat restrictive due to the limited options with integrated lead screw steppers. 

## Voron 2

The [Voron V2](http://vorondesign.com/voron2.4) is a modified coreXY design with a static bed and a gantry that moves along the Z axis. It is a much more complex build because it includes things such as 4-point gantry tramming to align to the print surface, dual MCUs, and other unique features. It is also designed to be fully enclosed so it prints ABS or similar filaments very well. Due to the linear rails the design is scalable all the way up to 350^3. More linear rails, larger print surface, and other V2-specific items make this printer more expensive and totals up to around \$1,500 USD. 

## Switchwire

The [Switchwire](http://vorondesign.com/voron_switchwire) is a Voron take on a classic Mendel (aka "bedflinger") design. It is a CoreXZ design so the print head is belt driven in both the X and Z axis eliminating the typical leadscrew Z drive allowing for very fast Z movement speeds and less weight on the grantry by moving the X motor to the frame.   The stiff 3030/3060 contructed frame is just large enough to cover the entire swing of the bed and allows for a natural enclosure. 

# Extruders and Variants

## Mobius (M4)

Mobius is the original Bowden extruder for Voron printers, designed to be mounted on the frame.  Highly optimized, dual gear, and very effective for Bowden setups.  Driven by a full-size or a compact "pancake" NEMA17 motor..

## Jetpack

Jetpack is a modified Mobius designed to be mounted on the X axis for a shorter Bowden.  Was designed as an intermediary solution to reduce the bowden tube lengths befor the introduction of Afterburner.  It is driven by a compact "pancake" NEMA17 motor.

## Afterburner

Afterburner is not specifically an extruder, but the collective name for the Voron direct-drive interchangeable toolhead system.

## Clockwork

Clockwork is the name given to the original extruder system for Afterburner.  It is a repackaged BMG dual-gear extruder driven by a compact "pancake" NEMA17 motor.  The Afterburner term is commonly used to refer to this extruder.

## Pocketwatch

Pocketwatch is the Afterburner Clockwork repackaged for the smaller size needed by the V0 printer.

## Galileo

Galileo is the newest extruder designed to fit on an Afterburner toolhead.  It is based on the [Orbiter](https://www.thingiverse.com/thing:4223085) extruder and incorporates a planetary gear reduction to allow a smaller housing size and even smaller motor to be used in order to reduce weight.

# Building the Printer

## Printing Parts

All Voron printers are strongly recommended to be printed in ABS or ABS+ for temperature resistance.  Questions?  [Check the FAQ](./faq.md#printing-parts)

## Ordering Parts

For every printer on the main webpage, There is a method to generate a bill of materials (BOM).  That is the definitive guide for what parts are required for that printer.  The BOM also references the sourcing guide.  The sourcing guide is a list of recommended vendors for the various components that are required to build a printer.  While there may be quantities listed on the sourcing guide, those numbers are not guaranteed to be accurate and we strongly recommend that people reference the BOM for specific quantities.

_Note:_ The generated BOM part numbers for Misumi extrusions are the exact part numbers.  Enter them into Misumi's website and they will return exactly what needs to be ordered, down to drilling holes and tapping ends.

There are a growing number of suppliers that are assembling kits to build Voron printers.  Outside of the sourcing guide, Voron does not implicitly endorse any specific vendor of Voron kits.

### Recommendations

* Get on Discord!  There is a very active community on the [Voron Discord Server](https://discord.gg/voron).
* When purchasing small items, buy extras (round up).  Having a few extra screws or connectors around may actually help you later.
* Check the [FAQ](./faq.md)
