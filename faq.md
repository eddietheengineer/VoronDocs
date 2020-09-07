# Frequently Asked Questions

## Voron General

### Should I read #official\_sourcing\_guide and #part\_printing\_guidelines, and watch #help\_videos?

Yes!

### Are CAD source files released?

Typically yes.  Sometimes the STLs are released before the CAD, but most printers have a complete CAD available.

### Can I get help for with my non-Voron printer?

Not typically.  If not building a Voron, the 3dp Discord is better.

### Ive never built a printer, what should I do?

Build either VORON model 100% to spec, you get a config that will work pretty close to out of the box, a wiring diagram, etc. It will also be easier for us to help you

### Do any Voron printers support dual extrusion / dual hot ends / tool changers?

There are no plans to release any of those at this time.  There are individual users doing independent testing, but nothing is officially supported.

### Why doesnt the VORON have a chamber heater

There are a few reasons

* Big company patents and lawyers
* Joe burning his house down
* Its really easy to screw up for someone that doesnt have great amounts of experience with properly controlling/mounting them
* If we spec something and people cheap out, there will be fires involved

### What firmware does the VORON use?

Klipper: Read this before asking any and all questions: https://www.klipper3d.org/Overview.html

### What are the requirements to get a serial for my printer?

You need to have completed cable management above the deck plate, toolhead doors attached and closed, and a video of a print in progress showing the complete printer, including these details, submitted to the Voron subreddit.

_Note: be sure to correctly flair your submission as a serial request or it may get overlooked. Mods try to process requests a couple of times a week so please be patient._

### Is the voron designed to print exotic materials?

No.

* A voron is made from printed abs parts and does not support being built with other materials.
* The voron does not have a heated chamber, therefore it is not designed to print exotic materials. Exotics such as peek require build chamber temperatures of over 100C to print properly, which will result in everything in the chamber self-destructing. Belts are good to 80C max, steppers around 90C, printed parts start deforming around 70C.
* Watercooling is not supported because of the risk associated with it, leaks and mains voltage don't play well with each other. You need a separate cable chain to properly run the tubing which would not fit inside the machine (XY is mostly the issue, but there is an issue with the Z also).
* Adding a chamber heater would exceed the current requirements of a standard home circuit (with buffer), a standard voron can draw up to 10A easily from the wall during warmup. Adding a water pump and a chamber heater will easily push it near a 15a current draw, as internal testing has determined a we need approximately 700w of heating power to warm the chamber to 75C (per multiple ansys simulations).
	* The true recommended chamber temp for PEEK is 130C, for True Nylon or PC (not hybrids or blends) is 100C, below this you will see delamination. This basicaly equates to putting your printer in an oven, youd want the least amount possible of the motion system in the "hot zone" and a ton of insulation. VORON is currently not designed for this, and it is not planned to be.
* This machine is intended such that it can be built with "garden tools", chamber heaters violate this, and add unnecessary risk to the end user.
* We recommend you purchase an industrial printer designed for this purpose if you intend to print with these materials so you dont end up with a fire on your hands.


## Build Planning

### Can I scale the V2 frame larger than 350^3?

Yes, but it will be more expensive, with a reduction in print quality, and much slower than the supported sizes. The machine was also never designed to support those sizes so you will run into structural issues. The VORON Design team does not endorse or support printers larger than 350 x 350 in the XY and 500 in the Z due to internal testing.

### Can I use these 4040 extrusions that I have from another project?

Yes, but be prepared to redesign nearly every part.

### Can I use my V-Slot extrusions from another project

Maybe, but highly discouraged. MGN9 Linear rails generally cannot sit properly on them and tend to fall into them.

### Why does the Voron use only 2020 extrusions?

Because 2020 is enough for the application. It’s not a CNC machine and the strength to weight/stiffness ratio is more than ideal for 3DP where no side loads or cutting forces are imparted.

_However_, the Switchwire uses 6030 and 3030 due to the frame design.

### Will full kits/hardware kits be avalable for purchase?

There are no plans by Voron Design to sell kits of any kind.  Other vendors are creating kits but none are endorsed by Voron.

### Do I need a screen on my printer ?

No - many of us use tablets running octoprint in the browser or a plugin like Nautilus.


## Printing Parts

### Can I print in (PLA, PETG, resin, etc.)?

Voron printers are designed to be able to print ABS and other materials that can require elevated chamber temperatures in excess of 60C.  As a result materials that have a heat deflection temperature or glass transition temperature of 90C or higher are strongly recommended for making the Voron components from.  While other materials may meet the requirements, from a cost/benefit perspective, ABS and ABS+ are the most recommended materials.

Most hobby-grade resin prints have issues with long-term dimensional stability.  Many of them will continue to shrink as they slowly dry out, making them unsuitable for long-term structural use.  There are many commercial resins that would likely work but there is no definitive list at this time.

If the prospective Voron owner is not currently able to print in ABS for any reason, we recommend looking at the Voron print-it-forward (PIF) program.  Individuals can submit a request for another Voron owner to print the minimum functional parts for them.  There are costs and wait times associated.

### What are the recommended accent parts?

The recommended accent parts are denoted with a "[a]_" in the filename. Many of these are still functional in nature and should still follow the recommended print settings.

### How much filament do I need?

Typical printers require approximately 1.5kg of the primary color and 0.3kg of the alternate color, assuming no failed or reprinted parts.  Most people end up reprinting a few parts and a few mods, so plan on 2kg of the primary color.

### Can you print voron parts using a volcano

VORON parts are designed with a 0.4mm nozzle in mind, it is not recommended to use a 0.4mm nozzle with a volcano, even though it is available


## Frame

### Do I need to get extrusions from Misumi?

No you can get them elsewhere but you may have issues with the slot profile. There are many different extrusion profile "standards" and the Misumi profile is what's recommended to deal with rail offsets, bolt head sizes, etc. as designed.

### What are the "TPW" and "LCP-RCP" options for the frame?

These are the options specified to have Misumi tap and drill the hex key access holes in your extrusions. You can remove these options and do this yourself to save ~$40 USD. You will need appropriate tapping tools, oil, and patience to do it correctly which may add back up to $40 when it's all complete.

### The HNTAJ5-5 nuts are expensive. Do I really need this many?

No, you can substitute ball spring post-assembly nuts from Ali just as easily in 99% of the manual. You need 16 narrow M5 t-nuts for the gantry ends. You can substitute all M3 nuts for ball spring post-assembly if desired. Short M5 nut locations

### Why do you recommend RobotDigg linear rails (chinese) vs a Hiwin or THK genuine rail?

* We are not imparting cutting forces onto the carriages on the rails (ie: side loads), so the low preload and ok tolerances are good for this application
* A Set of 7 rails is the cost of one genuine mid-grade THK rail.
* Clean all of your rails, then grease them (there are numerous videos on youtube on how to do this). Pick your best rail for the X axis, 2 for the Y, use the worst on the Z

### Can I substitute MGN(insert rail size here) for MGN9H rails?

No, VORON V0/V1/V2 are not designed for anything but a MGN9H

### Why does the VORON not using IGUS products?

IGUS bushings exhibit a phenomenon called stiction, therefore in small movements the bushings will actually stick instead of gliding, at small detail, this causes detrimental issues.  The amount of slop required is unfavorable, tolerances are quite poor.  Bushing life is low for the price when compared to Misumi and even standard chinese offerings.

### Using the number of washers shown in the manual, things are too tight or too loose

Depending on where you sourced your washers they may have different tolerances. The VORON is designed around 1mm thick shim washers, you can buy either 0.5mm or 1mm thick ones and adjust accordingly. Standard washers are sized as follows: 1mm +0.2mm -0.00mm usually.

### I cannot find MIC6 Aluminum anywhere, is there something else I can use?

Yes, try to find the following, they are all the same thing, with a different trade name:

* Mic 6
* Alpase K100-S
* Alca 5
* Vista Metals ATP 5
* Alimex 5083 (vendor is very important on this one)

Materials not supported, these are all not designed to take repeated heating and cooling cycles and will warp quickly:

* 6061
* 5052
* 5053
* 2024
* 7### series not listed above
* 5### series not listed above


## Wiring

### Why are the wiring recommendations so strict?

The wiring recommendations are made out of an abundance of caution to hopefully prevent electric shorts and fires.

### What is a good crimping tool to use for terminating wires?

Engineer PA-09, PA-20, or PA-21. Yes, it's worth the cost.

### What gauge wire should I use where?

The gantry wiring should be all 24 gauge wire except for the hot end heater, which should be wired with 20 gauge.  This will permit all of the wires to fit within the drag chains.  The power wiring (AC and DC) should be at least 20 gauge, preferably larger (18 or 16 gauge).

### PTFE or Silicone wire?

The BOM currently specifies silicone wire for bend and heat toleraance.  For an increased cost, PTFE wire is a option.  PTFE insulation is thinner and slicker, making it more effective in the drag chains.

### Do I need to reterminate my steppers to match the manual or some other documentation?

No. There is not a "standard" wire color order for these parts. If you decide to reterminate to change connector types or whatever, be sure to use the same order as before. The spec motors also come with a datasheet or card so you can double check your work. You can also use a multimeter to find wire pairs in the motor by measuring continuity between leads. Each lead should have continuity to the other lead in its pair.


## Electronics

### Why an SKR 1.4?  What about Turbo?

The BTT SKR controller is inexpensive and extremely capable for the purpose.  Either an SKR 1.3 or 1.4 is recommended and can be used.  While both controllers have different pin configurations, they use the same controller chip.  BTT is no longer producing the 1.3 and it will eventually be unavailable.

The Turbo version is certainly usuable, but the additional speed is not required since most of the computing is offloaded by the Raspberry Pi.

### Can I use sensorless homing?

The CoreXY configuration does not support sensorless homing since both motors are active for both X and Y.  For V1 and V2, there is an external Z endstop switch that is designed to set the Z distance based on the nozzle height so sensorless homing is not required.

### Can I use 0.9 degree stepper motors rather than the spec'ed 1.8 degree motors?

* They would not be recommended for the Z and E motors. These are already geared which give them better resolution. Going to 0.9 degree motors would mean they would then need twice as many steps to go the same distance as a 1.8 degree motor. This combined with microstepping results in more cpu load on your boards and would then start to limit how fast you can drive these.
* They may have some beneficial affect on the XY axis (AB motors) which don't have the gearing that the Z and E assemblies have. Don't expect miracles though, filament variance is another factor that starts to be an issue as well when attempting small detail.
	* While 0.9 motor can be a bit quieter, from all accounts in an enclosed Voron the fans are likely to make most of the noise. So any noise benefit would be negligible(edited)
	* Using the BOM spec ramps and klipper with 0.9deg steppers will limit your theoretical travel speeds greatly, just running 1/16 microstepping with 0.9deg XY motors and pressure advance with a 1.8deg stepper on the Extruder is enough to easily overwhelm the board.



## Parts

### Where should I buy my parts from?

A large portion of parts come from AliExpress, Arrow, Mouser, Digikey and Misumi.

### Can I substitute _this_ part for _that_ part?

Builders are welcome to make substitutions as they see fit but this printer is not a race to be as cheap as possible. It is designed to compete with many other high-end printers will still being affordable. Substituting parts may also have other unintended side effects and cause compatibility issues. Please feel free to ask for advice before any substitutions are made.

### Does the Voron Support the Super Volcano

No, its a case of [shit design and metal fatigue waiting to happen](https://www.reddit.com/r/3Dprinting/comments/blqw6s/i_believe_there_was_some_initial_concern_about/)

### Dragon standard flow or high flow?

The Dragon standard flow is capable of supporting nozzles up to 0.6mm.  If planning on using 0.8mm nozzles or larger, the high flow is recommended.

### What are the hammer nuts used for?

The hammer nuts are intended to be used with the panel clips to allow easier removal and reinstallation.  It is possible to apply some locktite and create quarter-turn fasteners.

### What is the Kapton Tape used for?

The inductive probe in the toolhead is somewhat heat sensitive.  The kapton tape is helpful to be applied to the inductve probe to protect it from radiant hot end heat.

### What lube should I use?

The currently recommended lube for the linear rails is Mobilux EP2.  Either Super Lube or EP2 is recommended for the extruder gears.

### What about the Clever3d PEI coated plate? It seems cool, and not having to apply the PEI sheet myself would be nice..

Several users have attempted them, and they are simply not workable with ABS. Testing showed they required a first layer temperature of at least 130C, which is approaching the failure temperature of the adhesive on the recommended Keenovo heater.  Their NON-PEI coated plates are a solid option though for those in Europe wanting to source a build plate.  If you own a PEI coated Clever3d bed, we recommend applying a sheet of your own PEI to it



## Assembly

### What are good brands for drivers to work with all of the fasteners?

Bondhus, Wiha, Wera

### How square does the frame need to be?

Measured on the outer diagonals, the frame should be within 2mm.

### What is a good tool for grinding flats on the 5mm rods?

A Dremel or bench grinder work well. A flat file can also work fine. Use eye protection when working with high RPM power tools and fragile cutting discs.

### How is the deck panel attached?

The deck panel is sandwiched between the DIN rails and the bed rails.  The M5 bolts go into the DIN rails, through the deck panel, and into nuts in the bed rails.

### Should I clean the rails?

Most linear rails are packaged with a simple machine oil applied to the rails and carriages for transport.  It is recommended that the rails be cleaned with isopropyl alcohol (IPA) to remove the machine oil and the proper grease applied.  If the linear rails are packaged with the carriages installed, the carriages should not be removed for cleaning.


