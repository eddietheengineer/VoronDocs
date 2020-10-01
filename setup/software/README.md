
# Software Installation

## OctoPrint

Install OctoPrint on the Raspberry Pi by following the instructions found at [OctoPrint Download](https://octoprint.org/download/)

Once installed, ssh to your Raspberry Pi (Using PuTTY on Windows or the terminal on MacOS) at the address `pi@octopi.local`.  The default password is 'raspberry'.  It is highly recommended to change the default password using the following process:

* Login to Raspberry Pi
* `sudo raspi-config` (password may be requested again)
* Select "Change User Password" to change the password

## Klipper

_External References:_

* [Klipper Installation Instructions](https://github.com/KevinOConnor/klipper/blob/master/docs/Installation.md)
* [SKR Installation Instructions](https://3dprintbeginner.com/install-klipper-on-skr-1-3-speed-up-your-prints/)

### Installation

Once at the command line of the Raspberry Pi, run the following commands to download and install the latest version of Klipper:

```
cd
git clone https://github.com/KevinOConnor/klipper
./klipper/scripts/install-octopi.sh
```

### Firmware Flashing

* [SKR 1.3](./skr13_klipper.md)
* [SKR 1.4](./skr13_klipper.md)
* [SKR mini e3 V1.2](./miniE3_v12_klipper.md)
* [SKR mini e3 V2.0](./miniE3_v20_klipper.md)
* [FLY FLYF407ZG](./flyf407zg_klipper.md)

### Klipper Octoprint Configuration

The OctoPrint web server needs to be configured to communicate with the Klipper host software. Using a web browser, login to the OctoPrint web page and then configure the following items:

1. Navigate to the Settings tab (the wrench icon at the top of the page)
2. Under "Serial Connection" in "Additional serial ports" add "/tmp/printer" then click "Save"
3. Open Settings tab and under "Serial Connection" change the "Serial Port" setting to "/tmp/printer"
4. In the Settings tab, navigate to the "Behavior" sub-tab and select the "Cancel any ongoing prints but stay connected to the printer" option, then click “Save”
5. From the main page, under the "Connection" section (at the top left of the page) make sure the "Serial Port" is set to "/tmp/printer" and click "Connect". (If "/tmp/printer" is not an available selection then try reloading the page)
6. Once connected, navigate to the "Terminal" tab and type "status" (without the quotes) into the command entry box and click "Send". The terminal window will likely report there is an error opening the config file - that means OctoPrint is successfully communicating with Klipper.

### Klipper Troubleshooting and Common Errors

#### Retrieve Log File

The Klippy log file (/tmp/klippy.log) contains debugging information.
M112 command in the OctoPrint terminal window immediately after the undesirable event.

There is a logextract.py script that may be useful when analyzing a micro-controller shutdown or similar problem.

```
mkdir work_directory
cd work_directory
cp /tmp/klippy.log .
~/klipper/scripts/logextract.py ./klippy.log
```

The script will extract the printer config file and MCU shutdown information to work_directory.

#### TMC UART Error

This appears when the communication between the TMC drivers and the MCU is not working. Typically this means that you have not powered the SKR board with 12-24V (TMC drivers didn’t boot), you haven’t plugged in the TMC steppers to the correct spots, or you forgot to add or remove a jumper as detailed above.

#### ADC Error

ADC stands for “Analog to Digital Converter” and is what is used to convert thermistor readings to temperatures for your hotend and heated bed. As a safety precaution, if Klipper is expecting a thermistor to be plugged in but it is reading an invalid reading (no thermistor = open, or 0 ohms for a shorted wire as closed), it will go in to this shut down mode. Double check to make sure your thermistors are plugged in to the correct boards and plugs.

#### Unable to Connect

Once the underlying issue is corrected, use the `FIRMWARE_RESTART` command to reset the firmware, reload the config, and restart the host software. Check MCU IDs match your printer.cfg.  _Make sure you get the paths right!_


## Recommended OctoPrint Plugins
* OctoKlipper
* Themeify
* TerminalCommands
* Bed Level Visualizer
* Print Time Genius


## Mainsail

___Coming Soon___

---
## Next: [Software Configuration](../configuration.md)
