# Sourcing Information

## Printing Parts

### Material

Voron printers are designed to be able to print ABS and other materials that can require elevated chamber temperatures in excess of 60C. As a result materials that have a heat deflection temperature or glass transition temperature of 90C or higher are strongly recommended for making the Voron components from. While other materials may meet the requirements, from a cost/benefit perspective, ABS and ABS+ are the most recommended materials.

Most hobby-grade resin prints have issues with long-term dimensional stability. Many of them will continue to shrink as they slowly dry out, making them unsuitable for long-term structural use. There are many commercial resins that would likely work but there is no definitive list at this time.

If the prospective Voron owner is not currently able to print in ABS for any reason, we recommend looking at the Voron print-it-forward (PIF) program. Individuals can submit a request for another Voron owner to print the minimum functional parts for them. There are costs and wait times associated.

### Colors and Quantities

The recommended accent parts are denoted with a "[a]_" in the filename. Many of these are still functional in nature and should still follow the recommended print settings.

If any file ends with "_x#", that is an indication that the part requires that quantity to be made for that machine.

Typical printers require approximately 1.5kg of the primary color and 0.3kg of the alternate color, assuming no failed or reprinted parts. Most people end up reprinting a few parts and a few mods, so plan on 2kg of the primary color.

### Print Settings

These are the recommended settings.

- Layer height: 0.2mm
- Extrusion width: 0.4mm, forced
- Infill pecentage: 40%
- Infill type: grid, gyroid, honeycomb, triangle, or cubic
- Wall count: 4
- Solid top/bottom layers: 5
- Supports: NONE

### Print It Forward (PIF)

If you are not able to print the ABS parts of a Voron yourself, there is a community-driven service called Print it Forward (PIF) in place. The goal of PIF is to provide a set of necessary structural parts for a Voron printer of your desire, printed on a Voron 3D Printer, showcasing their print quality. Every PIF-Provider undergoes a thorough vetting procedure in order to provide parts capable of demonstrating of what a Voron is capable of. PIF is a non-profit project, the pricing is set to compensate for the filament, energy and wear on the provider's rig.

More information and the current queue length can be found on the [PIF Website](https://pif.voron.dev/). There is also a separate channel on the Voron discord, where questions can be asked.


## Ordering Parts

For every printer on the main webpage, there is a method to generate a bill of materials (BOM).  That is the definitive guide for what parts are required for that printer.  The BOM also references the sourcing guide.  The sourcing guide is a list of recommended vendors for the various components that are required to build a printer.  While there may be quantities listed on the sourcing guide, those numbers are not guaranteed to be accurate and we strongly recommend that people reference the BOM for specific quantities.

*When purchasing small items, it is recommended to buy extras (round up). Having a few extra screws or connectors around may actually help you later.*

_Note:_ The generated BOM part numbers for Misumi extrusions are the exact part numbers.  Enter them into Misumi's website and they will return exactly what needs to be ordered, down to drilling holes and tapping ends.

There are a growing number of suppliers that are assembling kits to build Voron printers.  Outside of the sourcing guide, Voron does not implicitly endorse any specific vendor of Voron kits.

### Parts Selection / Alternates

When choosing extrusions, V-slot extrusions are discouraged.  This is due to the use of the MGN9 linear rail as the V-slot and width of the rail are very close and cause misalignment.  Vendors of extrusions other than Misumi are generally fine but verification of the extrusion profile is highly recommended.

If trying to keep costs down, the screen on any printer is entirely optional. Many builders solely use the web interface.

Builders are welcome to make substitutions as they see fit but this printer is not a race to be as cheap as possible. It is designed to compete with many other high-end printers while still being affordable. Substituting parts may also have other unintended side effects and cause compatibility issues. Please feel free to ask for advice before any substitutions are made.

More sourcing information can be found in the [sourcing FAQ](./sourcing_faq.md)

## Recommended Tools

* Set of metric hex wrenches ("keys") from at least 1.5 - 5. (Wiha, Wera , or Bondhus are preferred)
* Screwdrivers
* Crimpers
	* Molex
	* Ferrule
* Needle nose pliers
* Diagonal wire cutters, small
* Wire strippers from 16 gauge to 28 gauge

---

### Next: [The Build](./build/README.md)
