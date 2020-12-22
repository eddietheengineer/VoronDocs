# About Voron

All Voron printers are built using CoreXY or CoreXZ configurations.  No Cartesian motion systems to be found.  The following reviews some of common features of Voron printers.

## What a Voron does

### Frames

All V1 and V2 frames are constructed with 2020 aluminum extrusions.  The V0 is built with 1515 Makerbeam XL and the Switchwire is constructed with 6030 and 3030 extrusions.  The 2020 for the V1 and V2 is considered sufficient for the application.  3D printers are not CNC machines and the strength to weight / stiffness ratio is more than sufficient for 3D printing where no side loads or cutting loads are imparted.

### Motion Control - Klipper

All Voron printers are by default specified too use [Klipper](https://www.klipper3d.org/Overview.html) as the underlying control system. Klipper, in our case, uses a Raspberry Pi for all the computational-heavy tasks and sends a list of preprocessed orders to the controller board. This allows for high speed processing while still allowing inexpensive controllers.

### Serial Numbers

Getting a serial number for the Voron means something, it is highly encouraged. All that it takes is to have completed cable management above the deck plate, toolhead doors attached and closed, and a video of a print in progress showing the complete printer, including these details, submitted to the Voron [Subreddit](https://www.reddit.com/r/voroncorexy/).

*Note: be sure to correctly flair your submission as a serial request or it may get overlooked. Mods try to process requests a couple of times a week so please be patient.*

## What a Voron doesn't

### Chamber Heating

There are a few reasons Voron does not and will not officially support active chamber heating.

* Big company patents and lawyers
* Joe burning his house down
* Its really easy to screw up for someone that doesnt have great amounts of experience with properly controlling/mounting them
* If we spec something and people cheap out, there will be fires involved

### Exotic Materials (PEEK, PEI, etc.)

A Voron is made from printed abs parts and does not support being built with other materials. The voron does not have a heated chamber, therefore it is not designed to print exotic materials. Exotics such as peek require build chamber temperatures of over 100C to print properly, which will result in everything in the chamber self-destructing. Belts are good to 80C max, steppers around 90C, printed parts start deforming around 70C. Adding a chamber heater would exceed the current requirements of a standard home circuit (with buffer), a standard voron can draw up to 10A easily from the wall during warmup.

The true recommended chamber temp for PEEK is 130C, for True Nylon or PC (not hybrids or blends) is 100C, below this you will see delamination. This basicaly equates to putting your printer in an oven, you'd want the least amount possible of the motion system in the "hot zone" and a ton of insulation. VORON is currently not designed for this, and it is not planned to be.

This machine is intended such that it can be built with "garden tools", chamber heaters violate this, and add unnecessary risk to the end user. We recommend you purchase an industrial printer designed for this purpose if you intend to print with these materials so you don't end up with a fire on your hands.

### Watercooling

Watercooling is not supported because of the risk associated with it, leaks and mains voltage don't play well with each other. You need a separate cable chain to properly run the tubing which would not fit inside the machine (XY is mostly the issue, but there is an issue with the Z also).  Adding a water pump and a chamber heater will easily push it near a 15A current draw, as internal testing has determined you would need approximately 700W of heating power to warm the chamber to 75C (per multiple ansys simulations)

### Multimaterial

Voron does not currently support dual extrusion, dual hot ends, tool changers, or other such things (officially).  There are individual users doing independent development testing, but nothing is officially supported.

### Large Scale

Building any CoreXY printer (including Voron) larger than 350^2 will be more expensive, with a reduction in print quality, and print slower than the supported sizes. The Voron was also never designed to support those sizes so builders will likely run into structural issues. The VORON Design team does not endorse or support printers larger than 350 x 350 in the XY and 500 in the Z due to internal testing.

---

### Next: [Choosing the Printer / Extruder](./hardware/README.md)
