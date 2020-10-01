# Wiring Information

## Safety Note
When wiring your printer electronics, you will be working with line voltage wiring (120V / 220V AC). Always double check to make sure your printer is unplugged and the capacitors in the power supplies have discharged before touching any wire or terminal.

## Risk of Damage
**Never plug or unplug any device while the printer is powered.** In addition to being a safety hazard, it is very easy to damage electronic components.  In particular the stepper drivers can be easily damaged by connecting or disconnecting stepper motors while powered.

## Tips

* Depending on your level of expertise it may be useful to practice crimping and soldering before wiring everything up. Bad crimps are a major source of problems later on and sometimes hard to identify!
* Safety Mains cables should be properly dimensioned. Use at least 20 AWG for mains connections, even better would be 18 AWG.
* Buy a quality SSR, do not source one from China or your house will catch on fire (see Official Sourcing Sheet)! Add a 115-125°C thermofuse to your bed heater as an additional safety measure.
* Dont run your bed above 105°C, this greatly reduces the lifespan of the adhesive holding it onto the build plate. Additionally it is recommended to run a bead of high temperature RTV sealant around the edge of the heater.
* Connect ground to your bed! Connect a ground to your frame!

## Connectors

The recommended MicroFit 3.0 connectors are specced up to 5A and should be used for all connections to the stepper motors, hotend and limit switches The JST connectors are used for connections to the MCU board(s). Adding molex connectors to all stepper motors is useful. You can disconnect motors while moving the gantry manually to avoid damage to the MCU board(s). Use a 3pin MLX connector (see the official sourcing guide) to allow your bed to be removable without disconnecting from the SSR directly. The thermistor can use a 2pin microfit connector.

## Cables

The specced silicone wire has been chosen because: It is very high strand count, which means it has higher fatigue life. Silicone insulation withstands heat and is more flexible which is good in high movement applications. It is less prone to snagging on other wires or the walls inside the cable chain. Check your cable loom before installing the chains. You need at least: 8x 24AWG wires in the z chain (2 steppers) 4x 24AWG wires in the y chain (endstops) 7x 24AWG (probe, fans, thermistor) 2x 20AWG in the x chain (heater) - do not downsize these, they are oversized for safety reasons. You may add additional wires to your cable chains as a replacement in chase of wire breaks. However, these cables will be heated/cooled and moved around as much as your live cables and may be broken already when you need them! X/Y endstop connector can be strapped to the bottom of the joint. Just make sure the cable is long enough, be sure to install the cover to keep any prints that fly off from bonding to your endstops Buy some cable holders (e.g. with adhesive) to organize your cables in the electronics compartment. Keep in mind the adhesive fails over time due to exposure to above room temperature. Cables can be hidden in the rails. Optionally print cable covers for the rails.

## DC Power Supply Wiring
Many of the latest generation of Voron printers spec the use of two or more independent power supplies.  That can include 24V, 5V, and 12V power supplies sepending on configuration.

**Important!**  Connect the DC 0V (typically labelled V-) on all of your DC power supplies together to ensure they all have the same voltage reference.  If this is not done there may be difficult to diagnose issues (devices may not turn on or may be damaged due to exceeding voltage limits).

### Smaller Printers (V0)

Instead of multiple power supplies, the V0 uses a DC-DC converter to generate a 5V bus instead of a dedicated 5V power supply.

![](./images/dcdc-converter-wiring.png)

### Larger Printers (V1, V2, Switchwire)

Please see the associated assembly guides for power supply configurtions.

---
# Wiring Configuration / Setup

## Gantry Routing

While some extruder motors and inductive probes come with wire leads long enough to reach part or all of the way down the cable chain, resist the urge to use them.  The wires typically found in them are not rated for the constant bending encountered in the cable chains and may break much sooner than desired.  Terminate all connections to silicone or PTFE wire before entering the cable chain.

## Wire Terminals

Different controller boards use different terminal types.  The RAMPS boards use Dupont terminals but the SKR boards use JST-XH terminals.  If using an SKR board, a JST-XH connector kit is required with 2-pin, 3-pin, and 4-pin connectors (see the BOM).  Unlike Dupont connectors, JST-XH connectors are keyed and will only fit one orientation so pay close attention when inserting pins.

For wiring the stepper motors, keep the same wire color sequence that your stepper motors came with and use that same sequence for all stepper motors in the printer.  If the BOM spec motors from StepperOnline are used, the wires should be in the color order as shown in the wiring diagrams.

**Important:** If the motors are found later on to be going the wrong direction, repinning the connectors is _not_ required.  The direction can be inverted in the configuration later.

## Inductive Probe Wiring (V1, V2, Switchwire)

The BOM spec PL-08N inductive probe (and the alterate Omron probe) that is used for Z Tilt Adjust or Quad Gantry Leveling (V2) needs to be powered with 12-24V, not the typical 5V that is used for end stop switches.  This is critical because if powered with 5V the sense distance is reduced enough to cause a nozzle crash.

If not closely following the BOM spec, ensure that the inductive probe purchased is a normally closed (NC) version rather than normally open (NO).  The configuration cannot be changed as that is built specifically from the factory.  A normally open (NO) probe may cause crashes if a wire breaks.

### BAT85 Diode

Due to this voltage the output signal from the sensor is approximately the same voltage as the sensor is powered with.  If the sensor is powered with the common 24V, it will send 24V to an input on the MCU that is never intended to see more than 5V.  The BAT85 diode is used to alleviate this issue.  It is oriented so that when the probe signal wire is high (12-24V), not current will flow into the MCU input pin.  As a result the MCU will read HIGH voltage due to the internal pull-up resistor.  If the probe signal is LOW (0V), current will flow from the MCU input pin through the diode, through the probe, and to ground (V-).  This will pull the MCU pin low and trigger appropriately.

**Important:** The BAT85 diode should always be wired with the black band toward the probe, not toward the MCU.

Below is a circuit diagram with more details.

![](./images/inductive_probe_diode_diagram.png)

## Endstop Wiring

Endstops can be wired one of two ways: normally closed (NC) or normally open (NO).  For normally closed configurations, the endstop switch allows current to flow through when not triggered.  For normally open configurations, the endstop switch only allows current to flow through whe triggered.

While both of these configurations will work fine in an ideal world, normally closed (NC) configurations are more robust.  If a wire breaks or a terminal becomes disconnected, the printer will think the endstop has triggered and will stop movement before the toolhead crashes into the bed or frame. Note that you should always still observe the homing routine - an intermittent break in an X or Y wire can still result in a crash as the nozzle will drop to where it thinks the Z endstop is and instead hit the bed (not applicable to V0).

Wiring mechanical endstop switches for NC operation is easy as the BOM spec switches have 3 pins exposed.  With a multimeter, probe each combination of the three pins until a pair is found that has continuity (<10 ohms resistance) when the switch is not triggered (normal state), but does not have continuity (>10M ohms resistance) when the switch is triggered (depressed).  Typically the outer two pins are the NC pins, but should be verified prior to installation.

![](./images/endstop_switch_wiring.png)

## Controller (MCU) Wiring

Follow the links to the wiring configuration guides specific to your printer and controller selection.  There are other controllers on the market that may work (such as Duet), but those are not commonly used so standard configurations have not been developed.

### Voron 0
* [V0 - mini e3 V1.2](./v0_miniE3_v12_wiring.md)
* [V0 - mini e3 V2.0](./v0_miniE3_v20_wiring.md)

### Voron 1
* [V1 - SKR 1.3](./v1_skr13_wiring.md)
* [V1 - SKR 1.4](./v1_skr14_wiring.md)

### Voron 2
* [V2 - SKR 1.3](./v2_skr13_wiring.md)
* [V2 - SKR 1.4](./v2_skr14_wiring.md)
* [V2 - FLYboard FLYF407ZG](./v2_flyf407zg_wiring.md)

### Voron Switchwire
* [SW - mini e3 V2.0](./sw_miniE3_v20_wiring.md)
* [SW - Einsy Rambo](./sw_einsy_rambo_wiring.md)

## Additional Items

### Mini12864 Display (V1, V2, Switchwire)

If installing a Mini12864 display, please follow the Mini12864 Klipper Guide located in the [Additional](../../setup/additional/README.md) section.

### Using non-24V fans with a 24V powered MCU

It is possible to use the SKR (and possibly other controllers) to control fans, LED's, and other devices even when those devices use a different voltage.  The SKR, like most controllers, uses the (-) pin to control if a device is switched on or off.

For a given device, is the V+ is wired to an external power supply (e.g. 5V or 12V), and the V- is wired to the SKR, the fan can be switched on or off.  As mentioned above, this will _only_ work if the DC 0V of all of the power supplies is tied together.

Note: In the diagram below, only DC wires are shown.  Red represents V+, black represents V-.

![](./images/gnd_switch_example.png)

----
## Next: [Software](../software/README.md)
