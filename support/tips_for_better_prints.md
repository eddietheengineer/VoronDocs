# Tips for Better Prints

### References:

* https://hackmd.io/XdDG0_2vSr6Kwaz8aGk79A

## Filament Choice

3d printing filaments from different manufacturer will vary in formulation and physical properties which causes them to behave vastly different. Even filaments from the same manufacturer may show different characteristics depending on the filament color and sometimes even the batch of the filament.
Not all manufacturers will meet the dimensional tolerances they specify for their filaments, you may want to invest in some measuring tools and verify their claims.

When picking a filament include price and availability into your considerations:

* A “boutique material” may have a prohibitively high cost or limited availability… the one spool you got may print great, but it doesn’t do you any good once it’s empty.
* “Cheap as dirt” filament is often cheap for a reason, be mindful of particulates in the filament, dimensional tolerances and quality of the moisture seal.

If possible, try different filaments from different brands and find some that work for you and your printer. Once you found a filament stock spare spools depending on your printing habits.

Depending on your local climate you may want to take extra precautions when storing opened filament spools for longer periods of time. Unless you live in a dry climate consider purchasing a large airtight container and some desiccant packs for medium/long term storage.

If your printer is in a humid environment (your basement may qualify as humid) consider building a “filament dry box” to protect your filament at all times.

### [Printer maintenance is important](./maintenance/README.md)

### Preparation / Startup Routine

A consistent print preparation and startup routine is essential in achieving consistent print results.

1. Clean print chamber. Dust and debris will collect in your print chamber and may transfer to the print if left unchecked. Periodically remove any dust and debris by wiping down all surfaces or by the use of compressed air.
2. Clean print surface. The print surface needs to be dust, oil and fat free as those will impact print adhesion. Clean the print surface with a suitable degreaser before every print. Isopropyl alcohol (IPA) is readily available and an excellent degreaser.
3. Flex-plates / removeable surfaces. If you are using a flexplate, springsteel or other type of removeable print surfaces be mindful of it’s orientation and the printers state. Depending on orientation of the plate and temperature of the bed the surface may deform slightly different causing inconsistent print results. Always install the flex-plate in the same orientation and the same bed state (hot vs cold). Tests with springsteel sheets seem to suggest that they are best installed after the bed has reached temperature and had time to equalize. If you are placing it on a hot bed use appropriate PPE to prevent burn injuries.
4. Bed temperature. The bed temperature reading mat does not reflect the temperature of the print surface, rather it reads the temperature of the heater mat. In addition, the plates temperature might require an additional 10+ minutes to equalize.
5. Chamber temperature. The print chamber of a Voron 2 is passively heated by the print bed. As the temperature in the chamber has a direct impact on material expansion and some of the sensors found inside the printer let the temperature reach a stable point before starting a print. This process can take upwards of 30 minutes.
Set the bed temperature to the desired temperature for printing and let the printer “heat soak” until the chamber temperature reaches a stable point in the >40°C range.
6. Axis movement. Repeatedly moving the printer’s axis over the full range of movement can help with the consistency during leveling/homing and initial layers. This can be combined into the “heat soak” and used to prevent timeouts.
7. Homing and gantry leveling. The inductive probe used for Quad Gantry Leving (QGL) is sensitive to temperature changes. Ensure that the chamber temperature is stable before running the QGL. The QGL can run with the hotend at temperature or with a cold hotend, experiment to see what gives you the most consistent results for your printer. The final homing before the start of a print must be done with a fully heated hotend to ensure repeatability of the z position.
8. Hotend heating, ooze and purge. During heatup filament may ooze from the nozzle, remove this from the nozzle prior to the final homing operation. The ooze may cause inconsistency in the homing and transfer to the print.
Filament left in the heated zone of the hotend for prolonged period of times will deteriorate. Use slicer generated purge features (e.g. “skirts”) or dedicated purge line to fully remove the “toased” filament from the heated zone prior to printing any actual parts.

